# Cloud Infrastructure v1.0 - Apache2 Web Server

A modern, responsive web page showcasing a Cloud Infrastructure project deployed on an Apache2 Web Server running on a Linux Virtual Machine.

## 📋 Features

- **Modern Design**: Built with Tailwind CSS and Font Awesome icons
- **Responsive Layout**: Works seamlessly on desktop, tablet, and mobile devices
- **Glass-morphism UI**: Beautiful frosted glass effect styling
- **Apache2 Deployment**: Optimized for Linux VM hosting
- **Real-time Status**: System status indicators and service readiness badges

## 🛠️ Prerequisites

Before you begin, ensure you have:

- A Linux Virtual Machine (Ubuntu/Debian recommended)
- Root or sudo access
- Basic terminal knowledge
- Optional: Git for cloning the repository

## 📦 Installation & Setup

### 1. **Install Apache2**

SSH into your Linux VM and run:

```bash
sudo apt update
sudo apt install apache2 -y
```

### 2. **Start and Enable Apache2**

```bash
# Start the Apache2 service
sudo systemctl start apache2

# Enable Apache2 to start on boot
sudo systemctl enable apache2

# Verify Apache2 is running
sudo systemctl status apache2
```

### 3. **Deploy the Code**

Navigate to Apache2's web root directory:

```bash
cd /var/www/html
```

#### Option A: Copy the file directly

```bash
# From your local machine, copy the index.html to your VM
scp index.html username@your_vm_ip:/var/www/html/
```

#### Option B: Clone from repository (if using Git)

```bash
cd /var/www/html
sudo git clone https://github.com/Siddhesh-09/Linux-VM-with-Apache2-WebPage.git
cd Linux-VM-with-Apache2
```

#### Option C: Create and paste manually

```bash
# Create the file in Apache2's resource directory
sudo nano /var/www/html/index.html

# Paste the contents of index.html, then save (Ctrl+X, Y, Enter)
```

### 4. **Set Proper Permissions**

```bash
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
```

### 5. **Access Your Website**

Open your browser and navigate to:

```
http://your_vm_ip_address
```

or

```
http://localhost
```

(if accessing locally on the VM)

**To find your VM's IP address:**

```bash
hostname -I
```

## 🗂️ Project Structure

```
.
├── index.html          # Main webpage (this file)
└── README.md          # Project documentation
```

## ⚙️ Configuration

### Customize Your LinkedIn Profile Link

Edit the `index.html` file and find this line:

```html
<a href="https://www.linkedin.com" target="_blank" class="inline-block ...">
```

Replace `https://www.linkedin.com` with your actual LinkedIn profile URL:

```html
<a href="https://www.linkedin.com/in/your-username" target="_blank" class="inline-block ...">
```

### Change Title

Locate the `<title>` tag and update it:

```html
<title>Your Project Name | Live on Apache2</title>
```

## 🔧 Troubleshooting

### Apache2 Service Won't Start

```bash
# Check Apache2 configuration for errors
sudo apache2ctl configtest

# Restart the service
sudo systemctl restart apache2
```

### Permission Denied Errors

```bash
# Fix ownership
sudo chown -R www-data:www-data /var/www/html

# Fix permissions
sudo chmod -R 755 /var/www/html
```

### Cannot Access from Browser

1. Check if Apache2 is running: `sudo systemctl status apache2`
2. Verify the correct IP address: `hostname -I`
3. Check firewall settings:
   ```bash
   sudo ufw allow 80/tcp
   sudo ufw allow 443/tcp
   sudo ufw reload
   ```

### Files Are Not Showing

- Ensure `index.html` is in `/var/www/html/`
- Restart Apache2: `sudo systemctl restart apache2`
- Check file permissions: `ls -la /var/www/html/index.html`

## 🌐 Enabling HTTPS (Optional)

To secure your connection, install Let's Encrypt SSL certificates:

```bash
# Install Certbot
sudo apt install certbot python3-certbot-apache -y

# Generate SSL certificate
sudo certbot --apache -d yourdomain.com

# Access your site securely
https://yourdomain.com
```

## 📋 System Requirements

| Component | Requirement |
|-----------|------------|
| OS | Ubuntu 20.04+ / Debian 10+ |
| RAM | 512 MB minimum |
| Disk Space | 1 GB minimum |
| Apache2 | 2.4+ |
| Browser Support | All modern browsers (Chrome, Firefox, Safari, Edge) |

## 📝 Notes

- The page displays Python 3.14 Ready badge - customize this to match your actual environment
- Font Awesome icons are loaded from CDN - ensure internet connectivity
- Tailwind CSS is utilized via CDN for styling
- The background gradient can be modified in the `<style>` section

## 🚀 Deployment on Cloud Platforms

### Google Cloud Platform (GCP)

```bash
# SSH into your VM instance
gcloud compute ssh instance-name --zone=your-zone

# Follow installation steps above
```

### Amazon EC2

```bash
# SSH into your instance
ssh -i your-key.pem ec2-user@your-instance-ip

# Update package manager
sudo yum update -y

# Install Apache2
sudo yum install httpd -y

# Follow the setup steps above
```

### Azure Virtual Machines

```bash
# SSH into your VM
ssh username@your_vm_ip

# Follow installation steps above
```

## 📚 Useful Apache2 Commands

```bash
# Start Apache2
sudo systemctl start apache2

# Stop Apache2
sudo systemctl stop apache2

# Restart Apache2
sudo systemctl restart apache2

# Check Apache2 status
sudo systemctl status apache2

# View Apache2 logs
sudo tail -f /var/log/apache2/access.log
sudo tail -f /var/log/apache2/error.log

# Enable a module
sudo a2enmod module_name

# Disable a module
sudo a2dismod module_name
```

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Feel free to fork this repository, make improvements, and submit pull requests.

## 💬 Support

For issues or questions, please open an issue on the GitHub repository.

---

**Last Updated:** March 2026

**Author:** Siddhesh Khanorkar

**Repository:** https://github.com/Siddhesh-09/Linux-VM-with-Apache2-WebPage.git
