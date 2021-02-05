---
title: Testing PaperTrail versions in RSpec using ActiveSupport TimeHelpers
subtitle: ""
date: 2021-02-05T21:06:56.726Z
thumb_img_path: /images/screen_shot_2020-03-25_at_10.22.44_am.png
thumb_img_alt: Code example
content_img_path: ""
content_img_alt: ""
excerpt: Using ActiveSupport::Testing::TimeHelpers' `travel_to` to test
  PaperTrail behavior in a Rails application using RSpec.
template: post
---
I guess the screenshot header has the whole answer! Just wanted to put this snippet here since it came handy a couple times already; easy way to travel back in time using `travel_to` helpers to generate different versions of an object.

```
RSpec.describe Startup do
  include ActiveSupport::Testing::TimeHelpers
  
  describe '#version_at' do
    let(:startup) { create :startup }

    before do
      travel_to 30.day.ago do
        startup.update_attribute(:name, 'New Name')
      end

      travel_to 15.day.ago do
        startup.update_attribute(:name, 'Third Name')
      end
    end

    it 'successfully fetches the version' do
      expect(startup.versions.count).to eq 3
      expect(startup.paper_trail.version_at(30.day.ago).name).to eq 'New Name'
      expect(startup.paper_trail.version_at(15.day.ago).name).to eq 'Third Name'
    end
  end
end
```