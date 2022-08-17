# Setup

Example code is written directly into index.php.

#Database Creation

We will use the database to handle the redirection based on the shortcode. 
The following SQL creates a short_urls table in the MySQL database to store URL info (long URL, short code, hits, and create time). 

CREATE TABLE `short_urls` (
 `id` int(11) NOT NULL AUTO_INCREMENT,
 `long_url` varchar(255) COLLATE utf8_unicode_ci NOT NULL,
 `short_code` varchar(25) COLLATE utf8_unicode_ci NOT NULL,
 `hits` int(11) NOT NULL,
 `created` datetime NOT NULL,
 PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;


#Database configuration 

In the dbConfig.php, change the database credentials accordingly.

