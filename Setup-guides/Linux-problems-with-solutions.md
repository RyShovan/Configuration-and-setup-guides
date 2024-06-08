# Linux Problems with solutions

## Unable to find other OS in grub menu:
- check if you have *os-prober* package installed.
- if not first install it.
- now run the command `sudo os-prober`
- if you see it can detect the os, run `sudo nano /etc/default/grub`
- uncomment `GRUB_DISABLE_OS_PROBER=false` or add it if not exist then save the file and run `sudo update-grub`
- it should solve the problem.