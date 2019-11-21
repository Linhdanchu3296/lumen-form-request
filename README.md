# lumen-form-request
Laravel Form Request adaptation for Lumen framework

### How to install
```
composer require Linhdanchu/lumen-form-request
```

* Add the service provider in bootstrap/app.php

```
$app->register(Linhdanchu\Providers\FormRequestServiceProvider::class);
```

Next step is create your FormRequest and extends from Linhdanchu/Requests/FormRequest
### Example

```
<?php

namespace App\Http\Requests;

use Linhdanchu\Requests\FormRequest;

class StoreDeviceRequest extends FormRequest
{
	public function authorize()
	{
		return true;
	}

	public function rules()
	{
		return [
			'mac_address' => 'required|unique:devices,mac_address'
		];
	}
}
```

* Link for Laravel Form Request documentation

https://laravel.com/docs/5.4/validation#available-validation-rules

Enjoy!
