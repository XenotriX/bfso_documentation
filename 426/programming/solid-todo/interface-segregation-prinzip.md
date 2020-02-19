# Interface-Segregation-Prinzip

{% hint style="info" %}
Clients should not be forced to depend upon interfaces that they do not use.
{% endhint %}

Das Interface-Segregation-Prinzip oder Schnittstellenaufteilungsprinzip ist ein Begriff aus der Informatik. Es handelt sich um ein Prinzip des objektorientierten Entwurfs. Demnach sollen zu große Schnittstellen in mehrere Schnittstellen aufgeteilt werden, falls implementierende Klassen unnötige Methoden haben müssen. Nach erfolgreicher Anwendung dieses Entwurfprinzips müsste ein Modul, das eine Schnittstelle benutzt, nur diejenigen Methoden implementieren, die es auch wirklich braucht.

```php
<?php

interface NotifiableInterface
{
	public function getNotifyEmail() : string;
}

class Subscriber implements NotifiableInterface{
	public function subscribe()
	{
		// logic
	}	
	
	public function unsubscribe()
	{
		// logic
	}
	
	public function getNotifyEmail() : string
	{
		// logic
	}
}

class Notifications
{
	public static function send(NotifiableInterface $subscriber, $message){
		Mail::to($subscriber->getNotifyEmail())
			->queue($message);
	}
}
```

