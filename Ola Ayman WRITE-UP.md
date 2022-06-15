# Path of vulnerable file

Insert the file name with the path ex. /config/auth.php

- [mono_backend/composer.lock]

# \#1

## Description of Vulnerability

What is the vulnerability?
laravel/framework RCE.
<!-- 
        CWE-94 Improper Control of Generation of Code ('Code Injection')
        CVE 2022-31279
        CVSS 8.1 -->
    
laravel/framework @9.6.0 is a PHP framework for web artisans.

Affected versions of this package are vulnerable to Remote Code Execution (RCE) via an unserialized pop chain in __destruct in Illuminate\Broadcasting\PendingBroadcast.php and __call in Faker\Generator.php

When software allows a user's input to contain code syntax, it might be possible for an attacker to craft the code in such a way that it will alter the intended control flow of the software. Such an alteration could lead to arbitrary code execution.

## Impact of Vulnerability

What can happen if an attacker successfully exploits this vulnerability?

Existence of code syntax in the users data increases attacker's possibility to change the planned control conduct and execute arbitrary code.

## Exploitation

can be exploited by executing <?php system('ls') ?> in the burp repeater and the server will respond with the content returned by ls command, this test the existance of the vul. and then any adaquate code within the <? php ?> in the burp repeater will execute, this can lead to information disclosure and leaking of senstive data like all the paths of the files in server

## Fix (Code Snippet)


## Mitigation:
