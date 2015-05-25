---
layout: post
title:  "Issue on WP Migrate DB Pro and Wordpress 4.2.2"
date:   2015-05-25 15:20:00
categories: wordpress wp-migrate-db-pro
---
[Wordpress 4.2 tries to use utf8mb4 charactor set for the datebase][link] where it's possible.  
I found this would cause an error when you are migrating WP from one server to anohter with WP Migrate DB Pro plugin.

**Situation and Problem:**

1. Local mySQL does support utf8mb4
2. Remote server does not support utf8md4
3. Both WP were updated to version 4.2
4. Run WP Migrate DB Pro to migrate the data of the local WP into the remote WP
5. The plugin returns an error message saying "can't find xxxxxxxx.frm" and the migration process can't be completed


**Solution:**

- Change the local mySQL charactor set back to utf8 manually


**Update:**

- It seems that this error occurs in conjunction with WPML.

[link]:      https://make.wordpress.org/core/2015/04/02/the-utf8mb4-upgrade/