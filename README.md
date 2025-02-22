# absolute-to-relative-urls

The title says it all. So, if you were to use this library on a website like *http&#65279;://example.com/test/testing/*, you would get results like these:

1.
    * **Before:** http&#65279;://example.com/test/another-test/#anchor
    * **After:** ../another-test/#anchor
2.
    * **Before:** http&#65279;://example.com/wp-content/themes/twentyten/style.css
    * **After:** /wp-content/themes/twentyten/style.css
3.
    * **Before:** http*s*&#65279;://example.com/wp-content/themes/twentyten/style.css
    * **After:** http*s*&#65279;://example.com/wp-content/themes/twentyten/style.css
4.
    * **Before:** http&#65279;://google.com/test/
    * **After:** //google.com/test/
5.
    * **Before:** ../../../../../../../../#anchor
    * **After:** /#anchor
    * **After (`$output_type=1`):** ../../#anchor

**All string parsing**. *No* directory browsing.

## Usage

```php
<?php
echo absolute_to_relative_url('http://your-domain.com/dir/');
?>
```

or

```php
<?php
$instance = new Absolute_to_Relative_URLs('http://remote-site.com/');
 
echo $instance->relate_url('http://remote-site.com/dir/', false, 0);
?>
```
