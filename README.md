# security-header-php-htaccess
Security Header PHP and .htaccess

## _PHP_
~~~sh
    header('Server: " "');
    header('X-Frame-Options: DENY');
    header('X-XSS-Protection: 1; mode=block');
    header('X-Content-Type-Options: nosniff');
    header('Strict-Transport-Security: max-age=31536000; includeSubDomains');
    header('Referrer-Policy: same-origin');
    header('Permissions-Policy: geolocation=(), microphone=(), accelerometer=(), gyroscope=(), magnetometer=(), interest-cohort=()');
    header('X-Powered-By: " "');
    header('Content-Security-Policy: upgrade-insecure-requests');
~~~

## _.htaccess_
~~~sh
<IfModule mod_headers.c>
  Header always set Strict-Transport-Security "max-age=63072000; includeSubDomains; preload"
  Header always set X-XSS-Protection "1; mode=block"
  Header always set X-Content-Type-Options "nosniff"
  Header always set Referrer-Policy "no-referrer-when-downgrade"
  Header always set Expect-CT "max-age=7776000, enforce"
  Header set Access-Control-Allow-Origin "null"
  Header set Access-Control-Allow-Methods "GET,PUT,POST,DELETE"
  Header set Access-Control-Allow-Headers "Content-Type, Authorization"
  Header set Cross-Origin-Resource-Policy 'cross-origin'
  Header always set X-Frame-Options "SAMEORIGIN"
  Header set X-Powered-By " "
  Header always set Permissions-Policy "geolocation=(), microphone=(), accelerometer=(), gyroscope=(), magnetometer=(), interest-cohort=()"
  Header set Content-Security-Policy "upgrade-insecure-requests"
</IfModule>
~~~~
