# Magento 2 Mirror 

Quickly clone and install specific magento verison.  My crude approach at speeding up semi-automated docker installs.

# Stage 1 Github Files

## clone

swap 2.2.0 for release version

`git clone -b '2.2.0' --single-branch --depth 1 https://github.com/DominicWatts/magento2-mirror ./`

`rm .git -rf`

### or

## curl / tar

swap 2.3.3 for release version

`curl -LJO https://github.com/DominicWatts/magento2-mirror/archive/2.3.3.tar.gz`

`tar -zxvf magento2-mirror-2.3.3.tar.gz magento2-mirror-2.3.3`

`mv magento2-mirror-2.3.3/* ./`

`rm magento2-mirror-2.3.3 -rf`

`rm magento2-mirror-2.3.3.tar.gz`

# Stage 2 Magento repo files

## composer ##

`composer install`

# Stage 3 install

`php -d memory_limit=-1 bin/magento setup:install --admin-firstname Admin --admin-lastname User --admin-email dominic@xigen.co.uk --admin-user admin --admin-password test123 --base-url http://magento2.docker/ --backend-frontname xpanel --db-host db --db-name magento2 --db-user magento2 --db-password magento2 --language en_GB --currency GBP --timezone UTC --use-rewrites 1 --session-save files`

