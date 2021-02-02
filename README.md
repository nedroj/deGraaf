## Setup
1. npm install
2. composer install
3. php artisan key:generate
4. maak een .env bestand aan aan de hand van .env.example
5. verander de database informatie in .env naar je eigen informatie.
6. Maak database aan met de naam die in je .env staat
7. php artisan migrate

## Development
1. php artisan serve
2. npm run watch
3. Database aanzetten (XAMPP/WampServer/Laragon)

## Seeder
1. php artisan migrate:fresh
2. composer dump-autoload
3. php artisan db:seed


## Roles
1. In de web.php moeten routes beveiligd worden
2. ->middleware('verified') of ->middleware('auth') is om te kijken of een user ingelogd is
3. ->middleware('employee') kijkt of de gebruiker de rol van personeelslid heeft, admin's kunnen deze paginas ook gebruikern
4. ->middleware('admin') is voor paginas die alleen de admin kan bezoeken
5. ->middleware('notBlocked') is om te kijken of een ingelogde user geblokkeerd is. als dit zo is logt hij uit. Deze middleware moet alleen gebruikt worden op paginas waar een gebruiker voor ingelogd moet zijn

## Setup gmail
1. Go to the .env file
2. Find the lines
    1. MAIL_DRIVER=smtp
    2. MAIL_HOST=smtp.mailtrap.io
    3. MAIL_PORT=2525
    4. MAIL_USERNAME=null
    5. MAIL_PASSWORD=null
    6. MAIL_ENCRYPTION=null
3. change line 2.11. to MAIL_HOST=smtp.gmail.com
4. change toe mail port to MAIL_PORT=465
5. Enter the gmail account u want to use on lone 2.iv. it should look like this MAIL_USERNAME=yourmail@gmail.com
6. Enter the password of the gmail on line 2.v. It should look like this MAIL_PASSWORD=yourpassword
7. now you are going to your gmail account, and go to the settings and change the IMAP settings. This will give permission to other clients to send mails with your gmail account.
    1. go to settings
    2. go to all settings
    3. go to the tab with POP/IMAP
    4. find the section with IMAP-Access
    5. Select Imap activated
    6. save changes
8. Test with laragon mail service    

## setup google recaptcha
1. In the .env file there are 2 lines already there.
   1. GOOGLE_RECAPTCHA_KEY='enter key'
   2. GOOGLE_RECAPTCHA_SECRET='enter secret'
2. To create these keys go to https://www.google.com/recaptcha/admin/create.    
    1. select your type of reCAPTCHA.
    2. select domain
    3. enter the owner
3. copy the generated key paste on step 1.i. Do the same for the secret but paste it in 1.ii. 
   
