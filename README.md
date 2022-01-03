# angular-internationalization
<b>angular-internationalization - i18n</b>

<b>first of all , install requirements:</b>

    npm install @ngx-translate/core --save
    npm install @ngx-translate/http-loader --save
    npm install @biesbjerg/ngx-translate-extract --save
    
<b>next , import modules in app.module</b>
   
    import {TranslateModule,TranslateLoader} from '@ngx-translate/core'; 
    import {TranslateHttpLoader} from '@ngx-translate/http-loader';
    import {HttpClient, HttpClientModule } from '@angular/common/http';

    @NgModule({
    ...
    imports: [
    ...
    TranslateModule.forRoot({
      loader:{
        provide:TranslateLoader,
        useFactory:(http:HttpClient)=>{
          return new TranslateHttpLoader(http, './assets/translateFolder/','.json')
        },
        deps:[HttpClient]
      }
    })  

<b>you should define some translator file for each language in assets/translateFolder</b>


<b>for example the english translator file can be :</b>

    { 
      "home":{ 
        "Id":"0",
        "language":"English",
        "HelloWorld":"Hello world",
        "isSelected":"is selected" 
      }
    }
    
<b>and for spanish:</b>

    { 
      "home":{ 
        "Id":"1",
        "language":"Spanish",
        "HelloWorld":"Hola Mundo",
        "isSelected":"está seleccionado" 
      }
    }



    
