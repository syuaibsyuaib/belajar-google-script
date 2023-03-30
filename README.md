# Belajar google script
Transaksi data antara **Google Script** dengan **Github Page**.

*Github Page* hanya web statis yang mengandung kode javascript sebagai pengirim data menggunakan kode :
```javascript
fetch(url, {
  method: 'post',
  body: JSON.stringify(data)
})
.then(res => {
  return res.json()
})
.then(res2 => {
  console.log(res2)
})
```

Sedangkan di sisi *Google Script* akan diterima menggunakan kode:
```javascript
function doPost(e){
  const data = JSON.parse(e.postData.contents)
  return ContentService.createTextOutput("Telah diterima")
}
```

*Google Script* juga dapat terhubung dengan berbagai produk *google* diantaranya ialah *Google Sheets* dengan menggunakan kode:
```javascript
SpreadsheetApp.getActive().getRange('A2').setValue(data)
```
