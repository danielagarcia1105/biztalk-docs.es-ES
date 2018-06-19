---
title: Método DisplayUI de adaptador dinámico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9183d2ee-4265-4fee-9d1d-7e2462d8ff37
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd26bc5e5e344f53537e16135bf0a30b8b1443c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238676"
---
# <a name="dynamic-adapter-displayui-method"></a>Método DisplayUI de adaptador dinámico
Este método en el **IDynamicAdapterConfig** interfaz muestra la interfaz de usuario personalizada para el adaptador personalizado. Esto hace posible que el usuario consulte, seleccione e importe los archivos de compatibilidad relacionados en función de los servicios seleccionados en el proyecto de BizTalk.  
  
 En el adaptador de archivo, modifique el código dentro de la **displayUI** método del archivo AdapterManagement.cs para crear una interfaz de usuario personalizada (UI) para seleccionar el tipo de esquema que se va a Aceptar. Tras seleccionar un esquema, elija el archivo WSDL adecuado.  
  
 El código siguiente procede del **displayUI** método del archivo AdapterManagement.cs.  
  
```  
/// <summary>  
        /// Acquire wsdl(s) from which to build the user interface  
        /// </summary>  
        /// <param name="endPointConfiguration"></param>  
        /// <param name="owner"></param>  
        /// <param name="WSDLList">Array of custom UI's WSDL (returned)</param>  
        /// <returns></returns>  
        public Result DisplayUI(IPropertyBag endPointConfiguration,   
            IWin32Window owner,  
            out string [] WSDLList)   
      {  
            WSDLList = new string[1];  
            WSDLList[0] = GetResource("AdapterManagement.service1.wsdl");  
            return Result.Continue;  
        }  
```