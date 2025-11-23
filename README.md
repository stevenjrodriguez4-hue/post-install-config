## Post-Install Configuration Objectives

- Enable required **PHP extensions** for osTicket (mbstring, intl, gd, imap, xml, mysqli).
- Create the **MySQL/MariaDB database** and a dedicated DB user with least-privilege.
- Run the osTicket **web installer** and finalize base URL, system email, and admin account.
- **Harden** the install: set `ost-config.php` to read-only and remove/rename `/setup`.
- Configure **IIS** (Default Document, MIME types if needed, PHP handler) and verify site loads.
- Set up **Departments, Teams, Help Topics, SLAs**, and agent accounts.
- Configure **Email** (SMTP for outgoing, IMAP/POP for incoming) and test ticket flow.
- Validate end-to-end: user submits ticket → agent receives/assigns → agent replies/solves.

## Configuration Steps

1) **Verify PHP Extensions**
   - Open `php.ini` and ensure these are enabled (remove the `;` and save):
     ```
     extension=php_mbstring.dll
     extension=php_intl.dll
     extension=php_gd2.dll
     extension=php_imap.dll
     extension=php_xml.dll
     extension=php_mysqli.dll
     ```
   - **IIS Reset:** `iisreset` (Admin PowerShell)

2) **Create Database & User**
   - In MySQL/MariaDB:
     ```sql
     CREATE DATABASE osticket CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
     CREATE USER 'ost_user'@'localhost' IDENTIFIED BY 'StrongP@ss!';
     GRANT ALL PRIVILEGES ON osticket.* TO 'ost_user'@'localhost';
     FLUSH PRIVILEGES;
     ```
   - Note the DB name, user, and password for the installer.

3) **Run the Web Installer**
   - Browse to your site (e.g., `http://localhost/osticket`).
   - Pass environment checks, then enter:
     - **MySQL Settings:** `osticket`, `ost_user`, `StrongP@ss!`
     - **Admin User:** name, email, strong password
     - **System Email:** helpdesk@yourdomain.com (or placeholder)

4) **Secure the Installation**
   - Set `include/ost-config.php` to read-only:
     - File properties → Security → remove Write for Users (or `attrib +R ost-config.php`)
   - Delete or rename `/setup` directory.

5) **IIS Configuration**
   - **Default Document:** ensure `index.php` is listed and at/near the top.
   - **Handler Mappings:** confirm PHP is mapped to `*.php`.
   - Optional: enable **HTTP Redirect** if hosting under a subfolder.

6) **Initial osTicket Setup**
   - **Admin Panel → Agents:** create agents, assign to Departments/Teams.
   - **Manage → Help Topics:** e.g., “Password Reset”, “New Hardware”, “Access Request”.
   - **Manage → SLA:** create a basic SLA (e.g., Sev 1: 4h, Sev 2: 8h, Sev 3: 24h).
   - **Emails → Settings/Incoming Mail:** add IMAP/POP account if using email fetching.
   - **Emails → Outgoing:** set SMTP and send a test email.

7) **Validation**
   - From the end-user portal, submit a test ticket.
   - Assign it to a Team/Agent, add a response, and close it.
   - Confirm email notifications for new/updated tickets are received.

## Screenshots (add yours here)

> Place images in: `post-install-config/screenshots/` and reference them below.

- ![PHP extensions enabled](screenshots/01-php-extensions.png)
- ![MySQL database + user created](screenshots/02-mysql-db-user.png)
- ![osTicket installer success](screenshots/03-installer-complete.png)
- ![Config file set read-only](screenshots/04-config-hardened.png)
- ![IIS default document / handler](screenshots/05-iis-config.png)
- ![Help topics & SLA configured](screenshots/06-help-topics-sla.png)
- ![Test ticket lifecycle](screenshots/07-test-ticket.png)
