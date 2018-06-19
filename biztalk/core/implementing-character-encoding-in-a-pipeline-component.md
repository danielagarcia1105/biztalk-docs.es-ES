---
title: Implementación de codificación de caracteres en un componente de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], encoding
ms.assetid: 862b56da-ec14-41f9-b63c-42d81124e167
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bc95dc44fa4a4905affaad969c248aa4b76d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257052"
---
# <a name="implementing-character-encoding-in-a-pipeline-component"></a><span data-ttu-id="003e3-102">Implementación de codificación de caracteres en un componente de canalización</span><span class="sxs-lookup"><span data-stu-id="003e3-102">Implementing Character Encoding in a Pipeline Component</span></span>
<span data-ttu-id="003e3-103">Para admitir la codificación de caracteres personalizada, debe implementar una clase de codificación personalizada derivando de Microsoft .NET Framework **codificación** clase, a continuación, crear un componente de canalización de archivos sin formato personalizado mediante la herencia de los planos estándar Componente de desensamblador de archivos o el ensamblador de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="003e3-103">To support custom character encoding, you must implement a custom encoding class by deriving from the Microsoft .NET Framework **Encoding** class, then create a custom flat file pipeline component by inheriting from the standard Flat File Disassembler or Flat File Assembler component.</span></span> <span data-ttu-id="003e3-104">Puede proporcionar una nueva instancia de codificación para el motor de análisis invalidando el método virtual protegido **FFDasmComp.GetDataReader** tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="003e3-104">You can supply a new encoding instance to the parsing engine by overriding the protected virtual method **FFDasmComp.GetDataReader** as shown in the following example.</span></span>  
  
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
  
## <a name="using-predefined-encoding-classes"></a><span data-ttu-id="003e3-105">Usar clases de codificación predefinidas</span><span class="sxs-lookup"><span data-stu-id="003e3-105">Using predefined encoding classes</span></span>  
 <span data-ttu-id="003e3-106">Microsoft .NET Framework predefine los siguientes tipos de codificación que se pueden usar para construir el analizador:</span><span class="sxs-lookup"><span data-stu-id="003e3-106">The following encoding types are predefined by the Microsoft .NET Framework and can be used to construct the parser:</span></span>  
  
-   <span data-ttu-id="003e3-107">ASCII</span><span class="sxs-lookup"><span data-stu-id="003e3-107">ASCII</span></span>  
  
-   <span data-ttu-id="003e3-108">UTF7</span><span class="sxs-lookup"><span data-stu-id="003e3-108">UTF7</span></span>  
  
-   <span data-ttu-id="003e3-109">UTF8</span><span class="sxs-lookup"><span data-stu-id="003e3-109">UTF8</span></span>  
  
-   <span data-ttu-id="003e3-110">Unicode (UTF16)</span><span class="sxs-lookup"><span data-stu-id="003e3-110">Unicode (UTF16)</span></span>  
  
```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.UTF8));  
```  
  
## <a name="using-supported-code-pages"></a><span data-ttu-id="003e3-111">Usar páginas de códigos compatibles</span><span class="sxs-lookup"><span data-stu-id="003e3-111">Using supported code pages</span></span>  
 <span data-ttu-id="003e3-112">Use el siguiente código para admitir Shift-JIS (página de códigos 932).</span><span class="sxs-lookup"><span data-stu-id="003e3-112">Use the following code to support Shift-JIS (codepage 932).</span></span>  
  

```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.GetEncoding(932)));  
```  
  
## <a name="using-a-private-encoding-class"></a><span data-ttu-id="003e3-113">Usar una clase de codificación privada</span><span class="sxs-lookup"><span data-stu-id="003e3-113">Using a private encoding class</span></span>  
 <span data-ttu-id="003e3-114">Puede crear su propia clase de codificación que se deriva de la **System.Text.Encoding** clase abstracta y realizar su propia codificación y descodificación.</span><span class="sxs-lookup"><span data-stu-id="003e3-114">You can create your own encoding class that derives from the **System.Text.Encoding** abstract class and perform your own encoding and decoding.</span></span>  
  
```  
class MyEncoding : System.Text.Encoding  
{  
   // overriding methods omitted  
}  
  
XmlReader xr = docspec.Parser(new DataReader(new MyEncoding()));  
```  
  
## <a name="using-a-private-datareader-class"></a><span data-ttu-id="003e3-115">Usar una clase DataReader privada</span><span class="sxs-lookup"><span data-stu-id="003e3-115">Using a private DataReader class</span></span>  

 <span data-ttu-id="003e3-116">Puede crear sus propias [DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx) clase que implementa el `IDataReader` de interfaz y realiza lecturas sin crear ninguna codificación clases.</span><span class="sxs-lookup"><span data-stu-id="003e3-116">You can create your own [DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx) class that implements the `IDataReader` interface and performs reading without creating any encoding classes.</span></span>  
  
```  
class MyDataReader : IDataReader  
{  
   // Implement data reader functions  
   // ...  
}  
  
XmlReader xr = docspec.Parse(new MyDataReader());  
```  
  
## <a name="see-also"></a><span data-ttu-id="003e3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="003e3-117">See Also</span></span>  
 [<span data-ttu-id="003e3-118">Utilizar los motores de análisis y serialización</span><span class="sxs-lookup"><span data-stu-id="003e3-118">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)