[![npm version](https://badge.fury.io/js/%40fjnr%2Fngx-translate-po-http-loader.svg)](https://badge.fury.io/js/%40fjnr%2Fngx-translate-po-http-loader)

# Description
Load po files for use with `ngx-translate`

## Installation:

 ```
npm i @ngx-translate/core --save
npm i @d2p2com/ngx-translate-po-http-loader --save
 ```

## Usage:
```ts
import { HttpClient, HttpClientModule } from '@angular/common/http';

import { TranslateModule, TranslateLoader } from '@ngx-translate/core';
import { TranslatePoHttpLoader } from '@d2p2com/ngx-translate-po-http-loader';

export function createTranslateLoader(http: HttpClient) {
	return new TranslatePoHttpLoader(http, 'assets/i18n', '.po');
}

@NgModule({
	imports: [
		BrowserModule,
		HttpClientModule,
		TranslateModule.forRoot({
			loader: {
				provide: TranslateLoader,
				useFactory: createTranslateLoader,
				deps: [HttpClient]
			}
		})
	],
	bootstrap: [AppComponent]
})
export class AppModule { }
```

## Special thanks

This package is a fork of the [initial repository](https://github.com/biesbjerg/ngx-translate-po-http-loader) and [forked repository](https://github.com/FJNR-inc/ngx-translate-po-http-loader). Special thanks to them for their effort in this project.
