# How to disable fill and copy series in WPF Spreadsheet

This example illustrates how to disable fill and copy series in `Spreadsheet`.

[WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) has the built-in support to fill the values across the rows and columns by dragging the fill handle of the cell containing value or any formula within it. If you want to disable fill and copy series in spreadsheet by setting [AllowFillSeries](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.FillSeriesController.html#Syncfusion_UI_Xaml_Spreadsheet_FillSeriesController_AllowFillSeries) property of [FillSeriesController](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetGrid.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetGrid_FillSeriesController) to `false` in [WorkbookLoaded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_WorkbookLoaded) event.

``` c#
//To disable the fillseries
spreadsheet.WorkbookLoaded += Spreadsheet_WorkbookLoaded;
 
private void Spreadsheet_WorkbookLoaded(object sender, Syncfusion.UI.Xaml.Spreadsheet.Helpers.WorkbookLoadedEventArgs args)
{
   foreach(var sheet in args.GridCollection)
   {
       sheet.FillSeriesController.AllowFillSeries = false;             
   }
}
```

If you want to disable the fill and copy series in newly added sheet at run time, you can set the `AllowFillSeries` property of `FillSeriesController` to false in [WorksheetAdded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_WorksheetAdded) event.

``` c#
spreadsheet.WorksheetAdded += Spreadsheet_WorksheetAdded;
 
private void Spreadsheet_WorksheetAdded(object sender, Syncfusion.UI.Xaml.Spreadsheet.Helpers.WorksheetAddedEventArgs args)
{
    spreadsheet.ActiveGrid.FillSeriesController.AllowFillSeries = false;
}
```

Below is the screen shot when `AllowFillSeries` is `false`.

![AllowFillSeries is false](https://www.syncfusion.com/uploads/user/kb/wpf/wpf-48439/wpf-48439_img1.png)

Below is the screen shot when `AllowFillSeries` is `true`.

![AllowFillSeries is true](https://www.syncfusion.com/uploads/user/kb/wpf/wpf-48439/wpf-48439_img2.png)