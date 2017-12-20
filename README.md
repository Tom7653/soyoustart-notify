SoYouStart-Notify-Reborn
=================
Notify when a SoYouStart server is available

## Why a fork?

To work with the new site, I may add other things at some point.

## Building

    npm install

## Usage: Real from Server

Get the product reference from http://www.soyoustart.com/us/essential-servers.xml page, `data-ref=` attribute.

    ./soyoustart-notify.js 139caeg2 bhs

To silent output (usable in cron):

    NODE_SILENT=true ./soyoustart-notify.js 139caeg2 bhs

## Usage: Testing

Get the product reference from http://www.soyoustart.com/us/essential-servers.xml page, `data-ref=` attribute.

    ./soyoustart-notify-test.js 139caeg2 bhs

To silent output (usable in cron):

    NODE_SILENT=true ./soyoustart-notify-test.js 139caeg2 bhs

## Usage: Cron

Exmaple to check `SYS-IP-1` every 15 minutes, for `bhs` zone:

    crontab -e

    MAILTO=mail@example.com
    */15 * * * * NODE_SILENT=true git/soyoustart-notify/soyoustart-notify-zone.js 142casys4 bhs

Exmaple to check `SYS-IP-1` every 15 minutes, for any zone:

    crontab -e

    MAILTO=mail@example.com
    */15 * * * * NODE_SILENT=true git/soyoustart-notify/soyoustart-notify.js 142casys4
