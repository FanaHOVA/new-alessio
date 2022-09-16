---
title: 'Fixing Papertrail "Tried to load unspecified class:
  ActiveSupport::TimeWithZone"'
date: 2022-09-16T17:32:19.104Z
thumb_img_path: /images/85a4bcf1-bf7b-4168-abd0-c4c45d182752.avif
content_img_path: /images/85a4bcf1-bf7b-4168-abd0-c4c45d182752.avif
template: post
---
Ran into this error when doing `reify` on a papertrail version. Couldn't easily find a solution online, so thought I'd post it for future reference. Just add this to your `application.rb`:

`﻿config.active_record.yaml_column_permitted_classes = [ActiveSupport::TimeWithZone, ActiveSupport::TimeZone, Time, Date]`﻿