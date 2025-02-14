<!-- DO NOT EDIT THIS FILE! -->
<!-- Instead edit contrib/rocketchat.php -->
<!-- Then run bin/docgen -->

# Rocketchat Recipe

[Source](/contrib/rocketchat.php)



## Installing

Create a RocketChat incoming webhook, through the administration panel.

Require the new recipe into your `deploy.php`

```php
require 'contrib/rocketchat.php';
```

Add hook on deploy:

```
before('deploy', 'rocketchat:notify');
```

## Configuration

 - `rocketchat_webhook` - incoming rocketchat webook **required**
   ```
   set('rocketchat_webhook', 'https://rocketchat.yourcompany.com/hooks/XXXXX');
   ```

 - `rocketchat_title` - the title of the application, defaults to `{{application}}`
 - `rocketchat_text` - notification message
   ```
   set('rocketchat_text', '_{{user}}_ deploying {{branch}} to {{target}}');
   ```

 - `rocketchat_success_text` – success template, default:
  ```
  set('rocketchat_success_text', 'Deploy to *{{target}}* successful');
  ```
 - `rocketchat_failure_text` – failure template, default:
  ```
  set('rocketchat_failure_text', 'Deploy to *{{target}}* failed');
  ```

 - `rocketchat_color` – color's attachment
 - `rocketchat_success_color` – success color's attachment
 - `rocketchat_failure_color` – failure color's attachment

## Usage

If you want to notify only about beginning of deployment add this line only:

```php
before('deploy', 'rocketchat:notify');
```

If you want to notify about successful end of deployment add this too:

```php
after('deploy:success', 'rocketchat:notify:success');
```

If you want to notify about failed deployment add this too:

```php
after('deploy:failed', 'rocketchat:notify:failure');
```



## Configuration
### rockchat_title
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L70)





### rocketchat_icon_emoji
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L74)



```php title="Default value"
':robot:'
```


### rocketchat_icon_url
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L75)



```php title="Default value"
null
```


### rocketchat_channel
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L77)



```php title="Default value"
null
```


### rocketchat_room_id
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L78)



```php title="Default value"
null
```


### rocketchat_username
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L79)



```php title="Default value"
null
```


### rocketchat_webhook
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L80)



```php title="Default value"
null
```


### rocketchat_color
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L82)



```php title="Default value"
'#000000'
```


### rocketchat_success_color
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L83)



```php title="Default value"
'#00c100'
```


### rocketchat_failure_color
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L84)



```php title="Default value"
'#ff0909'
```


### rocketchat_text
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L86)



```php title="Default value"
'_{{user}}_ deploying `{{branch}}` to *{{target}}*'
```


### rocketchat_success_text
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L87)



```php title="Default value"
'Deploy to *{{target}}* successful'
```


### rocketchat_failure_text
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L88)



```php title="Default value"
'Deploy to *{{target}}* failed'
```



## Tasks

### rocketchat:notify
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L91)

Notifies RocketChat.




### rocketchat:notify:success
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L121)

Notifies RocketChat about deploy finish.




### rocketchat:notify:failure
[Source](https://github.com/deployphp/deployer/blob/master/contrib/rocketchat.php#L151)

Notifies RocketChat about deploy failure.




