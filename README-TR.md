<h2>PHP eklentisi nasıl derlenir?</h2>
<h4>Giriş</h4>
PHP uzantısının Linux işletim sistemlerinde nasıl derlendiğini açıklayan bir belgedir.

<ol>

<li>
<h5>LAMP'ı kurun.</h5>
<pre>https://bitnami.com/stack/lamp</pre>
</li>

<li>
<h5>Phpize dosyasını sisteme tanımlayın.</h5>
LAMP'ın yüklü olduğu dizinde <code>php/bin</code> yoluna gidin. Terminali açıp <code>sudo cp -i phpize /usr/local/bin/phpize</code> komutunu çalıştırın.
</li>

<li>
<h5>Derleyici paketleri yükleyin.</h5>
Ubuntu'da kurulu olmayan derleme paketlerini, terminalden <code>sudo apt-get install autoconf</code> komutunu kullanarak yükleyin.
</li>

<li>
<h5>PHP'nin kaynak kodunu indirin.</h5>
GitHub'daki çoğu uygulamada olduğu gibi, PHP hala geliştirme aşamasında olan bir kaynak koduna sahiptir, kaynak kodu PHP tarafından derlenebilecek tüm eklentileri içerir, bu yüzden PHP'nin kaynak kodunu indirmeniz gerekir. <code>https://github.com/php/php-src</code>
</li>

<li>
<h5>Hangi eklentiyi yüklemek istediğinize karar verin.</h5>
İndirdiğiniz PHP kaynak kodunda, <code>ext</code> adlı klasör derlenmeye hazır eklentiler klasörüdür. Bu klasörde ihtiyacınız olan eklentiyi Masaüstüne kopyalayıp yapıştırın.
</li>

<li>
<h5>Eklentiyi derleyin.</h5>
Kopyaladığınız eklenti klasörünü terminal de açın ve sırasıyla aşağıda ki komutları çalıştırın, LAMP kurulumunun gerçekleştiği dizin kısmını güncellemeyi ihmal etmeyin.
<pre>
phpize
./configure --with-php-config=<strong>LAMP kurulumunun gerçekleştiği dizin</strong>/php/bin/php-config
make
</pre>
</li>

<li>
<h5>Derlenmiş eklentiyi LAMP eklentileri arasına kopyalayın.</h5>
Kullanıma hazır eklenti, komutları yürütmekte olduğunuz klasördeki modüller klasöründe bulunur. <code>.so</code> uzantılı eklenti dosyasını, LAMP kurulumunun gerçekleştiği dizin içinde ki <code>php/lib/php/extensions</code> yoluna kopyalayın.
</li>


<li>
<h5>Eklentiyi php.ini dosyasında tanımlayın.</h5>
LAMP kurulumunun gerçekleştiği dizin içinde bulunan <code>php/etc</code> yolunda yer alan <code>php.ini</code> dosyasını metin editörü yardımıyla açın ve başında noktalı virgül olmayacak şekilde bir önce adımda kopyaladığınız eklenti adını sisteme tanımlayın. <code>extension=eklentiadi.so</code>
</li>

<li>
<h5>LAMP ‘ı yeniden başlatın, artık rahatlıkla kullanabilirsiniz.
</li>
</ol>
