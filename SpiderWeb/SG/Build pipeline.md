expect what build pipeline do? 
for one game, set appropriate version for each build.
config after upload to run suitable
which external entities? **CP User(Consumer Product vs End User), FE, Stove Uploader(PC Client), BE, Studio S3, its DB, DPMS API?, ONSTOVE S3, CDN, Stove PCClient, End User** 
Build pipeline vs build pipeline API difference?
features? 
launch: request to run uploader (like login)
register build: return build id and presign url

why need register build? presigned URLs S3
presigned URLs S3? grant temp access, time period, direct upload without server
DPMS? Version management service
