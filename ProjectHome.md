一个简单的使用actionscript3解析xlsx文件的类库。可以将excel中的表格数据读取为二维数组。

示例：
```

private var urlloader:URLLoader;
public function RxlsxTest()
{
	urlloader = new URLLoader();
	urlloader.dataFormat = URLLoaderDataFormat.BINARY;
	urlloader.addEventListener(Event.COMPLETE,urlloaderCompHandler);
	urlloader.load(new URLRequest("Book1.xlsx"));
}
private function urlloaderCompHandler(e:Event):void
{
	var excel:Excel = new Excel(urlloader.data as ByteArray);
	var sheet:Array = excel.getSheetArray();//得到表格数据
}

```