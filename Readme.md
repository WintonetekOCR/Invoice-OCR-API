# Invoice OCR Recognition API 

## Introduction 

## Source Code 
```C#
var client = new HttpClient();
var request = new HttpRequestMessage(HttpMethod.Post, "https://netocr.com/api/v2/recogInvoiveBase64.do");
var content = new MultipartFormDataContent();
content.Add(new StringContent("/9j"), "img");
content.Add(new StringContent("M***********g"), "key");
content.Add(new StringContent("3***********6"), "secret");
content.Add(new StringContent("20090"), "typeId");
content.Add(new StringContent("json"), "format");
request.Content = content;
var response = await client.SendAsync(request);
response.EnsureSuccessStatusCode();
Console.WriteLine(await response.Content.ReadAsStringAsync());
```

