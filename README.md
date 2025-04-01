# Paulya Website

This is the official website for Oleg Paulya (Paul Ya), a unique music initiative that ranges from classical to rock music, offering new interpretations of classical pieces with a rock edge.

## Project Structure

```
index.html
css/
    style.css
images/
    favicon.png
    paulya-abstract.png
    paulya-background.png
    paulya-collage.png
    paulya-logo.png
    paulya-performance.png
js/
    main.js
```

## Features

- **Hero Section**: Displays the Paulya logo and a subtitle.
- **Project Description Section**: Describes the Paulya project with an image and text.
- **Video Sections**: Showcases various performances with embedded YouTube videos.
- **Photo Gallery Section**: Displays a collage of images.
- **Footer Section**: Contains social media links and contact information.

## Deployment

This website is deployed on AWS using Lightsail.

## Usage

1. Clone the repository:
    ```sh
    git clone https://github.com/pvulya1/paulya_website.git
    ```

2. Navigate to the project directory:
    ```sh
    cd paulya_website
    ```

3. Open `index.html` in your browser to view the website locally.

## Deploying Website Files

Step 1: Prepare the Server

```sh
# Create a temporary directory in your home folder
mkdir -p ~/temp

# Set permissions for the web directory
sudo chown -R bitnami:bitnami /opt/bitnami/nginx/html/
sudo chmod -R 755 /opt/bitnami/nginx/html/
```

Step 2: Upload Files (from your local machine)

```sh
# Option 1: Using SCP (run this on your local machine)
scp -i your-key.pem -r /path/to/your/local/website/* bitnami@your-server-ip:~/temp/

# Option 2: Using SFTP client like FileZilla
# Connect to your server and upload files to ~/temp/
```

Step 3: Move Files to Web Directory

```sh
# Copy files from temp directory to web directory
sudo cp -r ~/temp/* /opt/bitnami/nginx/html/

# Set proper permissions
sudo chown -R bitnami:bitnami /opt/bitnami/nginx/html/
sudo chmod -R 755 /opt/bitnami/nginx/html/
```

Step 4: Restart Nginx

```sh
sudo /opt/bitnami/ctlscript.sh restart nginx
# Verify Nginx is running
sudo /opt/bitnami/ctlscript.sh status nginx
```



