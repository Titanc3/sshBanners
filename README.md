# sshBanners
**Disclaimer, this is meant only for connecting to linux machines**
## What is a **ssh banner**?
It is a .txt file that gets shown when you ssh into a device\
ex:
```
user@pc1:~$ ssh user@pc2.local
The authenticity of host 'pc2.local (xxx.xxx.xxx.xxx)' can't be established.
ED25519 key fingerprint is SHA256:xxx.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'pc2.local' (ED25519) to the list of known hosts.

          _____        _____________________________        _____
         /    /\      /  _________________________  \      /\    \
        /    / /     /  /\_______________________/\  \     \ \    \
       /    / /     /  / /                       \ \  \     \ \    \
      /    / /     /  / /                         \ \  \     \ \    \
     /    / /     /  /_/    ____   _____   ____    \_\  \     \ \    \
    /    / /      |  | |   |\ _|\ |\___/| /|_ /|   | |  |      \ \    \   
   /    / /       |  | |   | | | |||   ||| | | |   | |  |       \ \    \
  /    /_/        |  | |   | | | |||   ||| | | |   | |  |        \_\    \
  \    \ \        |  | |   | | | |||   ||| | | |   | |  |        / /    /
   \    \ \       |  | |   | |_| |||___||| |_| |   | |  |       / /    /
    \    \ \      |  |_|   |/__|/ |/___\| \|__\|   |_|  |      / /    /
     \    \ \     \  \ \                  _        / /  /     / /    /
      \    \ \     \  \ \       |\| /-\ _/        / /  /     / /    /
       \    \ \     \  \ \_______________________/ /  /     / /    /
        \    \ \     \  \/_______________________\/  /     / /    /
         \____\/      \_____________________________/      \/____/


user@pc2.local's password: 

Last login: Sun Dec 22 19:33:52 2024 from xxx.xxx.xxx.xxx
user@pc2:~$ 
```
The banner can be anything in ascii, it's just a txt file.

## How do you add the ssh banners?
First, download the banner you want from the banners folder and rename it to <ins>banner.txt</ins>

Now we get it to the target machine, you can use any way you want, google drive, flash drive, etc.\
If you want to use terminal you can use [scp](https://unix.stackexchange.com/questions/106480/how-to-copy-files-from-one-machine-to-another-using-ssh).

**The next step will delete any banner you previously had**\
Then, when in the directory with the banner on the target machine do:
```
sudo rm /etc/ssh/banner.txt
sudo mv banner.txt /etc/ssh/
```
Now, you should be done. just restart the target system, and the ssh banner will show on next boot.
```
sudo reboot
```
