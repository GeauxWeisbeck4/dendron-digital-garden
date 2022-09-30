---
id: zk2kqdtavnxncie8404ktu6
title: Supabase
desc: 'Supabase Notes for GeauxWeisbeck4.dev Version 2'
updated: 1664409854248
created: 1664406327985
---
# Supabase
- [x] Setup Project
- [ ] create User Management database in sql editor
- [ ] API Info
  - [x] Project URL: https://bilmvpykrzrcturghtyu.supabase.co
  - [ ] Anon public: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImJpbG12cHlrcnpyY3R1cmdodHl1Iiwicm9sZSI6ImFub24iLCJpYXQiOjE2NjQ0MDYwMzMsImV4cCI6MTk3OTk4MjAzM30.ViJKhhcEV-iovsSGOHaiGrBwG_fX1VpQitWa0jFFXhk
  - [ ] Service role:eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImJpbG12cHlrcnpyY3R1cmdodHl1Iiwicm9sZSI6InNlcnZpY2Vfcm9sZSIsImlhdCI6MTY2NDQwNjAzMywiZXhwIjoxOTc5OTgyMDMzfQ.eXz3FLeqeYfGlXzsSBl3NC4vHLYwuMqiL9GEUuxS-kA
  - [ ] qdFDUgzPYKdpEvrn1CbW+0N2xVd9ls+uiRpiHHFgHXN0KRJ2prc24qlpOQP0nDxu9+ZV7KDUj2ncNXWqRndzQA==


# User Management Database in SQL Editor
-- Create a table for public "profiles"
create table profiles (
  id uuid references auth.users not null,
  updated_at timestamp with time zone,
  username text unique,
  avatar_url text,
  website text,

  primary key (id),
  unique(username),
  constraint username_length check (char_length(username) >= 3)
);

alter table profiles enable row level security;

create policy "Public profiles are viewable by everyone."
  on profiles for select
  using ( true );

create policy "Users can insert their own profile."
  on profiles for insert
  with check ( auth.uid() = id );

create policy "Users can update own profile."
  on profiles for update
  using ( auth.uid() = id );

-- Set up Realtime!
begin;
  drop publication if exists supabase_realtime;
  create publication supabase_realtime;
commit;
alter publication supabase_realtime add table profiles;

-- Set up Storage!
insert into storage.buckets (id, name)
values ('avatars', 'avatars');

create policy "Avatar images are publicly accessible."
  on storage.objects for select
  using ( bucket_id = 'avatars' );

create policy "Anyone can upload an avatar."
  on storage.objects for insert
  with check ( bucket_id = 'avatars' );
