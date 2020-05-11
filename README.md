### Confituration Command Steps for Hangul (Input / Output)
1. sudo apt-get update -y
2. sudo apt-get install -y fonts-nanum
3. sudo apt-get install -y fonts-nanum*
4. fc-cache -f -v
5. sudo apt-get install -y nabi
6. sudo apt-get install -y im-config
7. sudo apt-get install -y zenity
8. sudo apt-get install -y fcitx-lib*
9. sudo apt-get install -y fcitx-hangul
10. im-config
   * confirm
   * yes
   * select "fcitx" & confirm
11. fcitx-configtool
   * "Input Method" : Hangul
   * Keyboard : Korean-Korean(101/104 key)


### Install XAMPP
1. Download XAMPP file from [XAMPP|https://www.apachefriends.org/index.html] site.
   - check the PHP version. Must be PHP5.
2. Change downloaded File's Execute Privilege & Execute
   - Installed Path : /opt/lampp
   > chmod +x ./xampp-linux-x64-5.6.23-0-installer.run
   > sudo ./xampp-linux-x64-5.6.23-0-installer.run
3. Set allow_url_include 
   - Config Path : /opt/lampp/etc/php.ini
   - Change Status from "Off" to "On" in "allow_url_include"

** ERROR Reporting **
1. "Failed to execute default Web Browser. Input/Output Error"
   - Method 1. Install Another Web Browser (Chrome, etc)
   - Method 2. execute "Go to Application" After default Web Browser


### Set DB
1. Start XAMPP
2. execute "phpMyadmin" in toolbar
3. create Database for DVWA


### Install DVWA
1. Download DVWA 1.9 source code on [Github|https://github.com/ethicalhack3r/DVWA/releases]
2. Unzip
   > Unzip DVWA-1.9.zip
3. Copy & paste 
   - From "/home/kali/Downloads" to "/opt/lampp/htdocs/
   > mv /home/kali/Downloads/DVWA /opt/lampp/htdocs/dvwa
4. Connect DVWA
   - result "Green" is Completed, but "Red" is not Completed in Setup Check
   > (Web Browser) localhost/dvwa


### Install DVWA for Not Completed Setup
1. Setup reCAPTCHA ( dependency : google accounts. )
   - login [reCAPTCHA|https://www.google.com/recaptcha/intro/v3.html] site.
   - input the label, domain & confirm
      > label : dvwa
      > domain : localhost
   - copy keys & insert "config.inc.php"
      > Path : /opt/lampp/htdocs/dvwa/config
      > site key (= Public Key): "6Ld5ovUUAAAAAAPf_9E9FoW4vo238IaxQe5IvLb3"
      > Secret key : "6Ld5ovUUAAAAAMpDoLfy_larN8ChPUBD-C3BIsee"
   - edit password for mysql in "config.inc.php"
2. Set Privilege "Write"
   > sudo chmod 777 /opt/lampp/htdocs/dvwa/hackable/uploads/
   > sudo chmod 777 /opt/lampp/htdocs/dvwa/external/phpids/0.6/lib/IDS/tmp/phpids_log.txt
3. Create Database just "click" next button

   