# This is a Flameshot Custom Uploader written in PHP.
I was looking around for Flameshot Custom Uploaders and found [flameshot-custom-uploader by CanCodes](https://github.com/cancodes/flameshot-custom-uploader) and thought that it was a bit too bulky and dependency reliant (nodejs/js and python required which I don't like either very much) so I made one in a language most web hosts support (php) and made an upload command with common tools that most operating systems have.

NOTE: This is my first php application i've "made" (took 99% of the code from first resource) so I would be more than grateful to get pull requests to improve the code or add features such as token auth.
## Command
`flameshot gui -p /tmp & wait $! && FILENAME=$(find /tmp -maxdepth 1 -name '*.png' -mmin -60 -print0 | xargs -0 ls -1 -t 2>/dev/null | head -n 1) && curl --location --request POST 'https://cdn.jordanplayz158.me' --form "upfile=@$FILENAME" | xclip -selection clipboard`
### Resources Used
https://www.php.net/manual/en/features.file-upload.php (Used the code from the top comment "CertaiN" from 7 years ago)
The internet to see the various functions I needed to know for this to work for my needs. (Modified the script to send the url in plaintext as a response (If there are no errors))