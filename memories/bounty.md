```
id: 658e0e5e-8baf-4cc5-af0b-adb1f39129ae
title: bounty
links:
  - b902bdae-e3bc-4b10-96e6-76765bf42263
```

# bug bounty programms

> When uploading image files, GitLab Workhorse passes any files with the extensions jpg|jpeg|tiff through to ExifTool to remove any non-whitelisted tags.
> An issue with this is that ExifTool will ignore the file extension and try to determine what the file is based on the content, allowing for any of the supported parsers to be hit instead of just JPEG and TIFF by just renaming the uploaded file.
> One of the supported formats is DjVu. When parsing the DjVu annotation, the tokens are evaled to "convert C escape sequences".
> [GitLab: RCE when removing metadata with ExifTool][1]

[1]: https://hackerone.com/reports/1154542
