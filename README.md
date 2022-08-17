# url_shortner
#This URL Shortener service takes a long URL and compresses it in a short link which is easier to share. 
Short URLs are created programmatically using PHP without any third party URL Shortener API.

Create Database Table
We will use the database to handle the redirection based on the shortcode. The following SQL creates a short_urls table in the MySQL database to store URL info (long URL, short code, hits, and create time).

CREATE TABLE `short_urls` (
 `id` int(11) NOT NULL AUTO_INCREMENT,
 `long_url` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
 `short_code` varchar(25) COLLATE utf8_unicode_ci NOT NULL,
 `hits` int(11) NOT NULL,
 `created` datetime NOT NULL,
 PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;


#URL Shortener Library (Shortener.class.php)
This class uses PDO Extension to work with the MySQL database, so, PDO object instance is required on initialization of Shortener class.


#Database Configuration (dbConfig.php)
PDO (PHP Data Objects) is used to connect and select the database. Specify the database host ($dbHost), username ($dbUsername), password ($dbPassword), and name ($dbName) as per your MySQL database server credentials.


#index.php( Create short url and redirect to long url - Sample file)
-Initialize Shortener class and pass the PDO object.
-Specify the long URL which you want to convert in a short link.
-Call the urlToShortCode() function to get the short code of the long URL.
-Create short URL with URI prefix and short code.

redirect to long url:-
-Retrieve the short code from the query string of the URL, or from the URI segment.
-Call shortCodeToUrl() function to get the long URL by the short code.
-Redirect user to the original URL.

