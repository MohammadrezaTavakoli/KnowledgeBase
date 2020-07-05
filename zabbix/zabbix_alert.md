The installation Guide of zabbix is available in:
--Zabbix Official Installation Guide.

Setting The Zabbix Alert Via Telegram guide:
--Zabbix-in-Telegram

Configuring The Media Type Screenshots in zabbix 4.4:
--This is The config for Sending To the User












-This config is For Sending The message to the group











-Create The Action For the your Media.
--Add you trigger to the condition:

--Then add your wanted operations to it:
set you operations with the things you want.





--Then the Recovery Operations:
set your operations again for the recovery.

Add The appropriate Media Type to Your user:
note: one for sending to the user and another one for sending to group


After That you should see this in Administration → Users → selected user → Media


Notes:
--setting up the Media is different from the doc because The Github Repo is a bit old.
--Use The Socks5h Option in zbxtg_settings.py if you use tor and live in iran.
--install the python library packages with the user zabbix
--add the zabbix user to the sudoers group.
	sudo usermod -a -g sudoers zabbix
--the zabbix user in the linux system must has permission to read and write.
	Chmod g+w myfolder
<<CRITICAL NOTE>>
	Do not chown The file system to zabbix user.
--set the default shell for zabbix user in “/etc/passwd”
	you can use either chsh command or changing the passwd file manually.
--install the requirements.txt file with the sudo -H flag(user: zabbix)

Test the script with the zabbix user before using it with zabbix:
	test with zabix user
	for sending to user:
		sudo -u zabbix python zbxtg.py "@username" test test
	for sending to group:
		sudo -u zabbix python zbxtg_group.py "Group Name" test test

