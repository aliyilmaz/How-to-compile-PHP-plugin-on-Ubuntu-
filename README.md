<h2>How to compile PHP plugin on Ubuntu?</h2>
<h4>Introduction</h4>
It is a document describing how the PHP extension is compiled in Linux operating systems.

<ol>

<li>
<h5>Install LAMP.</h5>
<pre>https://bitnami.com/stack/lamp</pre>
</li>

<li>
<h5>Define the phpize file to the system.</h5>
Go to the <code>php/bin</code> path in the directory where LAMP is installed. Turn on the terminal here and run <code>sudo cp -i phpize /usr/local/bin/phpize</code>
</li>

<li>
<h5>Install compiler packages.</h5>
Install compile packages that are not installed in Ubuntu from the terminal with the <code>sudo apt-get install autoconf</code> command.
</li>

<li>
<h5>Download the source code of PHP.</h5>
As with most applications in GitHub, PHP still has a source code that is still in development, the source code contains all the plug-ins that can be compiled by PHP, therefore you need to download the source code of PHP. <code>https://github.com/php/php-src</code>
</li>

<li>
<h5>Decide which plug-in you want to install.</h5>
In the PHP source code that you downloaded, the folder named <code>ext</code> is the plug-ins folder ready to compile. Copy and paste the plug-in you need in this folder to the Desktop.
</li>

<li>
<h5>Compile the plugin.</h5>
Open the add-in folder that you copied to the desktop with the terminal and run the following commands respectively. Do not forget to update the directory part of the LAMP installation.
<pre>
phpize
./configure --with-php-config=<strong>The directory where the LAMP installation took</strong> place/php/bin/php-config
make
</pre>
</li>

<li>
<h5>Copy the compiled add-in between LAMP add-ins.</h5>
The ready-to-use plug-in can be found in the modules folder in the folder where you applied the commands. Copy the <code>.so</code> extension plug-in file to the <code>php/lib/php/extensions</code> path in the directory where the LAMP installation occurs.
</li>


<li>
<h5>Define the add-in in the php.ini file.</h5>
Open the <code>php.ini</code> file located in the <code>php/etc</code> path in the directory where the LAMP installation takes place. Type the name of the add-in that you copied in the previous step without a semicolon. <code>extension=extensionname.so</code>
</li>

<li>
<h5>Restart LAMP, you can now use it easily.
</li>
</ol>
