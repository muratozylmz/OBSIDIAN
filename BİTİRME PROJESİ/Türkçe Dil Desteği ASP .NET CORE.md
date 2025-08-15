### Program.cs dosyası içine:

``` cs
var cultureInfo = new CultureInfo("tr-TR"); 
CultureInfo.DefaultThreadCurrentCulture = cultureInfo; 
CultureInfo.DefaultThreadCurrentUICulture = cultureInfo;
```
 kodunu ekliyoruz ve bu kadar

### Program.cs'in başına da: 
```css
using System.Globalization;
```
komutunu ekliyoruz ve bitti.