function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Orders");
  var data = JSON.parse(e.postData.contents);
  sheet.appendRow([
    new Date(),
    data.name,
    data.shirtType,
    data.childMedium,
    data.childLarge,
    data.adultS,
    data.adultM,
    data.adultL,
    data.adultXL,
    data.adult2XL,
    data.adult3XL
  ]);
  return ContentService.createTextOutput("Success");
}
