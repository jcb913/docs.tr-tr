---
title: Veri kümesi şema bilgileri XSD olarak yazma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: b2012b32b0751bc093b9b3267cbbfc2e1a408156
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761005"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Veri kümesi şema bilgileri XSD olarak yazma
Şeması yazabilirsiniz bir <xref:System.Data.DataSet> olarak XML Şeması Tanım Dili (XSD) şeması, böylece, olan veya olmayan bir XML belgesi ilgili veri taşıyabilir. XML şeması bir dosyaya, bir akış yazılabilir bir <xref:System.Xml.XmlWriter>, veya bir dize; kesin türü belirtilmiş oluşturmada yararlıdır **DataSet**. Hakkında daha fazla bilgi için kesin türü belirtilmiş **DataSet** nesneleri bkz [yazılan veri kümeleri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Bir tablo sütunu XML Şeması nasıl temsil belirtebilirsiniz kullanarak **ColumnMapping** özelliği <xref:System.Data.DataColumn> nesnesi. Daha fazla bilgi için bkz: "XML öğeleri, öznitelikleri ve metin sütunları eşleme" [XML verileri olarak yazma DataSet içeriği](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Şeması yazmak için bir **DataSet** bir dosyaya XML şeması olarak akışı veya **XmlWriter**, kullanın **WriteXmlSchema** yöntemi **DataSet**. **WriteXmlSchema** sonuç XML Şeması hedef belirten bir parametre alır. Aşağıdaki kod örnekleri XML Şeması yazma göstermektedir bir **DataSet** bir dosya adı içeren bir dize geçirerek bir dosyaya ve <xref:System.IO.StreamWriter> nesne.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 Şeması almak için bir **DataSet** ve bir XML Şeması dize olarak okuma ve yazma, kullanma **GetXmlSchema** aşağıdaki örnekte gösterildiği gibi yöntemi.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DataSet içinde XML kullanma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [XML Verileri Olarak DataSet İçeriği Yazma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [Türü Belirtilmiş DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [DataSets, DataTables ve DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
