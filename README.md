# Klipper_backup
Klipper backup for ender 3 v2

11.1.2023 modit: Capricorn, yellow springs, klipper, all-metal single gear extruder

---

https://lazarofilm.gitbook.io/3d-printing/creating-a-github-backup-for-klipper

Next backups
Next time you want to backup your printer settings, you need to SSH into your pi and type:

cd ~/klipper_config/

git add .

git commit -m "backup"

git push -u origin master

Enter your GitHub credentials and you're done!

----

Restore your settings

Oops! Something happened and you need to go back to your settings you backed up in GitHub. It's okay, take a deep breath. 
There are multiple ways to access your backup. 
Copy on GitHub.com
You can simply go to your repo on GitHub.com and see all your settings, you can copy/paste any line and replace it in your current settings file. This is useful if you only need to go replace a section of your document. 
Restore with git
If you need to completely restore your settings in the already existing local folder: 

cd ~/klipper_config/

git fetch -all

git reset --hard origin/master

!!WARNING!! This will delete all your settings in your printer folder and replace them with your backup. You will lose any change that was not backed up!


If you are starting from a new install and need to restore your settings from your previous setup:

cd ~

git clone [Your-GitHub-Repo-URL]
