# Admin-theme
cool theme


## LAMP
`$sudo apt-get install tasksel`
`$sudo tasksel install lamp-server`

## CURL
`$sudo apt-get install curl`

## Enable mods
`$sudo a2enmod rewrite`
`$sudo systemctl restart apache2`

## Create folder theme
`$sudo chmod -R 777 [theme folder]`

## Creating Virtual Host work.com
`$sudo subl /etc/apache2/sites-available/theme.dev.conf`

#/etc/apache2/sites-available/theme.dev.conf contains following lines
`<VirtualHost *:80>`
		`ServerName theme.dev`
		`DocumentRoot /var/www/html/[theme folder]/`

		`<Directory /var/www/html/[theme folder]>`
			`AllowOverride All`
			`Require all granted`
		`</Directory>`
`</VirtualHost>`
			
## Enable that site
`$sudo a2ensite theme.dev`
`$service apache2 reload`

## fix hosts file	
`$sudo subl /etc/hosts`

`            #/etc/hosts contents following lines                                `
            `127.0.0.1       theme.dev`
		
	
	
## Change default server directory *OPTIONAL!
sudo subl /etc/apache2/sites-available/000-default.conf

and change the following line to what you want:

`DocumentRoot /var/www/html`

`Also do a`
`sudo leafpad /etc/apache2/apache2.conf`
`and find this`

`<Directory /var/www/>`
`Options Indexes FollowSymLinks`
`AllowOverride None`
`Require all granted`
`</Directory>`

and change /var/www/ to your preferred directory //mine is /var/www/html/work/public

and save it.
After you saved your changes, just restart the apache2 webserver and you'll be done :)
`$sudo service apache2 restart`

## Make theme to be the landing (localhost) site instead of apache2 /*optional
`$sudo a2dissite 000-default`
## this is to enable it 
`$sudo a2ensite 000-default`


## [ youtube](https://www.youtube.com/watch?v=A6TdaRIsG6g)
## [Apache command line](https://www.cyberciti.biz/faq/ubuntu-linux-start-restart-stop-apache-web-server/)
// check lôi apache  `$journalctl | tail`


