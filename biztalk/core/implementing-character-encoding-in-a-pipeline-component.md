---
title: "Implementación de codificación de caracteres en un componente de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], encoding
ms.assetid: 862b56da-ec14-41f9-b63c-42d81124e167
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bc95dc44fa4a4905affaad969c248aa4b76d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-character-encoding-in-a-pipeline-component"></a>Implementación de codificación de caracteres en un componente de canalización
Para admitir la codificación de caracteres personalizada, debe implementar una clase de codificación personalizada derivando de Microsoft .NET Framework **codificación** clase, a continuación, crear un componente de canalización de archivos sin formato personalizado mediante la herencia de los planos estándar Componente de desensamblador de archivos o el ensamblador de archivo sin formato. Puede proporcionar una nueva instancia de codificación para el motor de análisis invalidando el método virtual protegido **FFDasmComp.GetDataReader** tal como se muestra en el ejemplo siguiente.  
  
```  
/// <summary>  
/// Gets a data reader instance  
/// </summary>  
/// <param name="dataStream">Data stream</param>  
/// <param name="dataEncoding">Data encoding</param>  
/// <param name="detectEncodingFromByteOrderMarks">Detect encoding from a byte order mark</param>  
/// <returns>IDataReader instance</returns>  
      protected override IDataReader GetDataReader(Stream dataStream, Encoding dataEncoding, bool detectEncodingFromByteOrderMarks)  
      {  
         // Delegate call to the base implementation passing fixed UTF-7 encoding  
         return base.GetDataReader(dataStream, new CustomEncoding(), false);  
      }  
```  
  
## <a name="using-predefined-encoding-classes"></a>Usar clases de codificación predefinidas  
 Microsoft .NET Framework predefine los siguientes tipos de codificación que se pueden usar para construir el analizador:  
  
-   ASCII  
  
-   UTF7  
  
-   UTF8  
  
-   Unicode (UTF16)  
  
```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.UTF8));  
```  
  
## <a name="using-supported-code-pages"></a>Usar páginas de códigos compatibles  
 Use el siguiente código para admitir Shift-JIS (página de códigos 932).  
  

```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.GetEncoding(932)));  
```  
  
## <a name="using-a-private-encoding-class"></a>Usar una clase de codificación privada  
 Puede crear su propia clase de codificación que se deriva de la **System.Text.Encoding** clase abstracta y realizar su propia codificación y descodificación.  
  
```  
class MyEncoding : System.Text.Encoding  
{  
   // overriding methods omitted  
}  
  
XmlReader xr = docspec.Parser(new DataReader(new MyEncoding()));  
```  
  
## <a name="using-a-private-datareader-class"></a>Usar una clase DataReader privada  

 Puede crear sus propias [DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx) clase que implementa el `IDataReader` de interfaz y realiza lecturas sin crear ninguna codificación clases.  
  
```  
class MyDataReader : IDataReader  
{  
   // Implement data reader functions  
   // ...  
}  
  
XmlReader xr = docspec.Parse(new MyDataReader());  
```  
  
## <a name="see-also"></a>Vea también  
 [Utilizar los motores de análisis y serialización](../core/using-the-parsing-and-serializing-engines.md)