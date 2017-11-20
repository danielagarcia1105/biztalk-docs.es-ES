---
title: "Método DisplayUI de adaptador dinámico | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9183d2ee-4265-4fee-9d1d-7e2462d8ff37
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd26bc5e5e344f53537e16135bf0a30b8b1443c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-adapter-displayui-method"></a><span data-ttu-id="aeb23-102">Método DisplayUI de adaptador dinámico</span><span class="sxs-lookup"><span data-stu-id="aeb23-102">Dynamic Adapter DisplayUI Method</span></span>
<span data-ttu-id="aeb23-103">Este método en el **IDynamicAdapterConfig** interfaz muestra la interfaz de usuario personalizada para el adaptador personalizado.</span><span class="sxs-lookup"><span data-stu-id="aeb23-103">This method on the **IDynamicAdapterConfig** interface displays the custom user interface for the custom adapter.</span></span> <span data-ttu-id="aeb23-104">Esto hace posible que el usuario consulte, seleccione e importe los archivos de compatibilidad relacionados en función de los servicios seleccionados en el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="aeb23-104">This enables the user to view, select, and import the related supporting files based upon the selected services into their BizTalk project.</span></span>  
  
 <span data-ttu-id="aeb23-105">En el adaptador de archivo, modifique el código dentro de la **displayUI** método del archivo AdapterManagement.cs para crear una interfaz de usuario personalizada (UI) para seleccionar el tipo de esquema que se va a Aceptar.</span><span class="sxs-lookup"><span data-stu-id="aeb23-105">In the file adapter, modify the code within the **displayUI** method of the AdapterManagement.cs file to create a custom user interface (UI) for selecting the type of schema to accept.</span></span> <span data-ttu-id="aeb23-106">Tras seleccionar un esquema, elija el archivo WSDL adecuado.</span><span class="sxs-lookup"><span data-stu-id="aeb23-106">After a schema is selected, choose the appropriate WSDL file.</span></span>  
  
 <span data-ttu-id="aeb23-107">El código siguiente procede del **displayUI** método del archivo AdapterManagement.cs.</span><span class="sxs-lookup"><span data-stu-id="aeb23-107">The following code is from the **displayUI** method of the AdapterManagement.cs file.</span></span>  
  
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