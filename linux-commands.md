**Linux Commands for DevOps**
**File & Directory**
1.pwd → Show current directory
pwd
/home/ubuntu

2.ls -lah → List files with details
ls -lah
-rw-r--r-- 1 user user 1.2K Feb 18 notes.txt

3.cd dir/ → Change directory
cd /var/log

4.mkdir dir/ → Create directory
mkdir project

5.rm -rf dir/ → Delete directory
rm -rf project

**File Operations**
1.cp file1 file2 → Copy file
cp file1.txt backup.txt

2.mv file1 file2 → Move/rename file
mv old.txt new.txt

3.cat file.txt → Show contents
cat notes.txt

4.head -n 5 file.txt → First 5 lines
head -n 5 notes.txt

5.tail -f file.txt → Last lines, follow live
tail -f app.log

**Users & Permissions**
1.whoami → Show current user
whoami
ubuntu

2.chmod 755 file.sh → Change permissions
chmod 755 script.sh

3.chown user:group file.txt → Change ownership
chown devops:admin file.txt

**Process Management**
1.ps aux → List processes
ps aux | grep nginx

2.kill -9 PID → Kill process
kill -9 1234

3.top → Monitor live processes
top

**Networking**
1.ping host → Test connectivity
ping -c 4 google.com

2.curl url → Fetch data from URL
curl http://localhost:8080
Hello World

3.ss -tuln → Show listening ports
ss -tuln
LISTEN 0 128 *:22 *:*

4.scp file user@host:/path → Copy file to remote
scp notes.txt ubuntu@192.168.1.10:/home/ubuntu/

**Disk & Storage**
1.df -h → Disk usage
df -h
Filesystem Size Used Avail Use% Mounted on
/dev/sda1   50G  20G   28G  42% /

2.du -sh dir/ → Directory size
du -sh logs/
120M logs/

**System Monitoring**
1.uptime → System load & uptime
uptime
12:46:01 up 5 days, load average: 0.12, 0.08, 0.05

2.free -m → Memory usage
free -m
             total   used   free
Mem:         7972   2345   5627

**Logs**
1.tail -f logfile → Follow logs live
tail -f /var/log/syslog

2.grep "error" logfile → Search for errors
grep "error" app.log
ERROR: Connection failed

**Scheduling**
1.crontab -e → Edit cron jobs
Example: Run backup daily at midnight
0 0 * * * /home/ubuntu/backup.sh
