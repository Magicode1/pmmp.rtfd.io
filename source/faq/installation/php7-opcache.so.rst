Failed loading opcache.so php7
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This will happen when the installer is not used or when PocketMine-MP was moved.
This can be fixed with a single command.::

    sed "s/^zend_extension=.*opcache.so/zend_extension=$(find $(pwd) -name opcache.so | sed 's/\//\\\//g')/g" bin/php7/bin/php.ini | tee bin/php7/bin/php.ini

or manually by editing the ``bin/php7/bin/php.ini`` file.

1. Find ``opcache.so`` in the bin directory.
2. Edit ``bin/php7/bin/php.ini`` and replace everything after ``zend_extensions=`` with the full path of opcache.so
