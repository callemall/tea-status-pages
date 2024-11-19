# tea-status-pages

This repo holds the status pages when the web app (cea-desktop) is down.

- [Scheduled maintenance page](https://s3.amazonaws.com/cea-error-pages/maintenance.html) - This shows planned maintenance events. Maintenance mode must be manually triggered in Heroku.
- [System down error page](https://s3.amazonaws.com/cea-error-pages/error.html) - This shows for unplanned events when the system goes down.

Both pages are hosted on an S3 bucket: https://us-east-1.console.aws.amazon.com/s3/buckets/cea-error-pages

These pages retrieve data from the status.io API to display on the page. The credential to the Text-Em-All status.io account can be found [on the engineering wiki](https://sites.google.com/call-em-all.com/engineeringoperationswiki/contact-info?authuser=0#h.p_2_vfmYqglTNj).

## How to Update the Contents of the Error or Maintenance Pages

Please follow these instructions carefully to ensure the update is done correctly.

1. Download the latest version of the .html page you want to update from the [S3 bucket](https://us-east-1.console.aws.amazon.com/s3/buckets/cea-error-pages)
1. Make the desired changes and test them locally. Commit the changes to this repo.
1. Ensure the filename matches the name .html inside the bucket
1. Upload the .html to the bucket.
1. **IMPORTANT: In the permissions section, make sure Predefined ACLs is set to “Grand public-read access”. Otherwise, users will NOT be able to access the page.**
1. Click upload.
1. Test your changes by clearing your cache and going to the Object URL for the page

# Resources

- [Guide to updating status.io messages (Incidents vs Maintenance)](https://docs.google.com/document/d/1wp1BLBJq0KWVw31sUlQ7hVIxYAyFJxTIOBCybZ_h1AE/edit?tab=t.0)
- [Status.io](https://status.io/)
- [Status.io credentials](https://sites.google.com/call-em-all.com/engineeringoperationswiki/contact-info?authuser=0#h.p_2_vfmYqglTNj)
- [Text-Em-All status page](https://status.text-em-all.com/)
