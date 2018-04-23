# How to display values of several RTF fields in a single XRRichText control


<p><strong>Problem:</strong><br />
I am creating a data-aware report. The source data table has several columns containing RTF text. I need to concatenate the contents of these columns and display it in a single XRRichText.</p><p><strong>Solution:<br />
</strong>As you probably know, RTF strings cannot be concatenated directly (strResult = strSource1 + strSource2) because it will result in invalid RTF content. Instead, utilize special RTF-aware API to accomplish this task. Our XtraRichEdit Suite provides you with this API. In v2011 vol 1 we have implemented the non-visual <a href="http://search.devexpress.com/?q=RichEditDocumentServer&p=T0|P0|0&d=2943"><u>RichEditDocumentServer</u></a> component (in previous versions use the <a href="http://documentation.devexpress.com/#WindowsForms/clsDevExpressXtraRichEditRichEditControltopic"><u>RichEditControl Class</u></a> instead). You can use its <strong>RtfText</strong> property and <strong>Document.AppendRtfText()</strong> method (see the <a href="http://documentation.devexpress.com/#CoreLibraries/DevExpressXtraRichEditAPINativeSubDocument_AppendRtfTexttopic"><u>SubDocument.AppendRtfText Method</u></a>). Thus, handle the <strong>XRRichText.BeforePrint </strong>event, obtain current RTF field values via the <a href="http://documentation.devexpress.com/#XtraReports/DevExpressXtraReportsUIXtraReportBase_GetCurrentColumnValuetopic"><u>XtraReportBase.GetCurrentColumnValue Method</u></a>, concatenate them by using the aforementioned API and assign the resulting RTF to the <a href="http://documentation.devexpress.com/#XtraReports/DevExpressXtraReportsUIXRRichText_Rtftopic"><u>XRRichText.Rtf Property</u></a>.</p>

<br/>


