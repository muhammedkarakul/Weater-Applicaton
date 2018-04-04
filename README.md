# Clima
Bu uygulama Udemy platformunda iOS uygulama geliştirme eğitimleri veren Angela Yu'nun eğitiminden faydalanarak yapılmıştır.

Uygulamayı denemek için zip olarak indirin ve klasörden çıkarın. Pod dosyaları gitignore ile projeye dahil edilmemiştir. Pod dosyalarını projeye dahil etmek için öncelikle sisteminizde Cocoapods kurulu olmalıdır. Cocoapods sistemde kurulu ise terminal ekranına;

```
pod install 
```

yazarak projede kullanılan third-party frameworkleri projeye dahil etmiş olursunuz. Eğer bu işlemi gerçekleştirmezseniz uygulama çalışmaz!

## Bitmiş Uygulama
![Finished App](https://github.com/londonappbrewery/Images/blob/master/Clima.gif)

## Fix for Cocoapods v1.0.1 and below

```ruby
post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['SWIFT_VERSION'] = '3.0'
      config.build_settings['MACOSX_DEPLOYMENT_TARGET'] = '10.10'
    end
  end
end
```

## Fix for App Transport Security Override

```XML
	<key>NSAppTransportSecurity</key>
	<dict>
		<key>NSExceptionDomains</key>
		<dict>
			<key>openweathermap.org</key>
			<dict>
				<key>NSIncludesSubdomains</key>
				<true/>
				<key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
				<true/>
			</dict>
		</dict>
	</dict>
```


Copyright 2016 London App Brewery
