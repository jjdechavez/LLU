# Play around on Timezone with your machine

You want to test with different timezone

You can use `timedatectl` command
or use `timedatectl list-timezones` to list all available timezones

If you are lokking some specific timezone you can pipe it with grep `timedatectl list-timezones | grep Australia`

To Set your timezone
sudo timedatectl set-timezone <your_time_zone>

How to check your current timezone
`timedatectl status`

it would print out
`
[jerald@cassini projects]$ timedatectl status
               Local time: Lun 2023-05-22 14:26:13 PST
           Universal time: Lun 2023-05-22 06:26:13 UTC
                 RTC time: Lun 2023-05-22 06:26:13
                Time zone: Asia/Manila (PST, +0800)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no
`
