---
title: "Método GetSchema del adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c83340c-a775-435c-9633-3a692611e99e
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c40e698b3c373aa4e10a8de2362650a42e71a1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-getschema-method"></a>Método GetSchema del adaptador
Supongamos que el archivo WSDL al que se hace referencia contiene solo referencias a esquemas y ningún esquema integrado. En este caso, utilice la **GetSchema** método de la **IAdapterConfig** interfaz para cargar un esquema al que hace referencia desde dentro de un archivo WSDL.  
  
 En el ejemplo de adaptador de archivo, modifique el código en el **GetSchema** método de AdapterManagement.cs para devolver todos los archivos XSD externos que no están incluidos en los archivos WSDL.  
  
 El código siguiente procede del **GetSchema** método del archivo AdapterManagement.cs. Aquí devuelve NULL porque el archivo Service1.wsdl contiene esquemas integrados. Si ése no era el caso, se debe devolver una cadena correspondiente a un archivo de esquema XSD.  
  
```  
/// <summary>  
        /// Acquire externally referenced xsd's  
        /// </summary>  
        /// <param name="xsdLocation">Location of schema</param>  
        /// <param name="xsdNamespace">Namespace</param>  
        /// <param name="XSDFileName">Schmea file name (return)</param>  
        /// <returns>Outcome of acquisition</returns>  
        public Result GetSchema(string xsdLocation,  
                                string xsdNamespace,  
                        out string xsdSchema)   
      {  
            xsdSchema = null;  
            return Result.Continue;  
        }  
```