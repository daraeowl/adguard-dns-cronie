# adguard-dns-cronie
this simple cronjob will run every 60 minutes to bind your ip to the adguard-dns provider, it makes a normal petition to the url provided by them on their website.

I'm currently using Arch Linux but this follows the same logic to every distro.

# 1 step - > First we will install cronie to make our cronjobs work on the system. 

sudo pacman -S cronie

# 2 step - > edit the crontab file 
 you can choose the editor you wish with the following command, following the crontab one to the file.

**EDITOR=nano** crontab -e

# 3 step - > add your configuration, in this example we will run this cronjob every 1 hour since sometimes my ISP will change my IP every now and then.


0 * * * * curl https://linkip.adguard-dns.com/linkip/2337366b/hPlVal2Ab3RzsL6YNGhISc97HBZd9LXf200zknikciH >/dev/null 2>&1

make sure to replace your URL with the one they provide in the configuration site of adguard dns.

![image](https://user-images.githubusercontent.com/33108535/228714096-f925c8c0-ce5a-45b7-84d8-a63bf275dc63.png)

Do not forget to change your DNS configuration, this can be done within the computer or the router, this is on you.
# 4 step -> make sure your cronie is up and running with the following commands.
sudo systemctl enable cronie
sudo systemctl start cronie

**sudo systemctl status cronie -> this one will show your cronie status and if correct it will look something like this.**
![image](https://user-images.githubusercontent.com/33108535/228714839-5f7646bf-cb8a-41cd-9fd2-f063185527a7.png)
