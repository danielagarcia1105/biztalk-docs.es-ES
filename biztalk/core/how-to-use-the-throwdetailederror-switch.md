---
title: "Cómo usar el modificador ThrowDetailedError | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90929015e2d1d0567af0ccc5c51c6aae450d49c8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-throwdetailederror-switch"></a><span data-ttu-id="003ba-102">Cómo usar el modificador ThrowDetailedError</span><span class="sxs-lookup"><span data-stu-id="003ba-102">How to Use the ThrowDetailedError Switch</span></span>
<span data-ttu-id="003ba-103">Si se produce un error, el cliente Web recibe un tipo genérico **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="003ba-103">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="003ba-104">Para depurar el servicio Web publicado, puede agregar un modificador al archivo Web.config para controlar el nivel de los detalles de la excepción devueltos desde el servicio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="003ba-104">To debug your published Web service, you can add a switch to the Web.config file to control the level of the exception details returned from the published Web service.</span></span>  
  
 <span data-ttu-id="003ba-105">El archivo Web.config contiene un modificador de la configuración de aplicación, **ThrowDetailedError**.</span><span class="sxs-lookup"><span data-stu-id="003ba-105">The Web.config file contains an application setting switch, **ThrowDetailedError**.</span></span> <span data-ttu-id="003ba-106">**False** es el valor predeterminado de **ThrowDetailedError**.</span><span class="sxs-lookup"><span data-stu-id="003ba-106">**False** is the default setting for **ThrowDetailedError**.</span></span> <span data-ttu-id="003ba-107">Si cambia la configuración a **True**, el servidor proxy devuelve información de excepción interna para el cliente Web, lo que le permite depurar el servicio Web publicado.</span><span class="sxs-lookup"><span data-stu-id="003ba-107">If you change the setting to **True**, the server proxy returns inner exception information to the Web client enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="003ba-108">El código XML siguiente muestra el **ThrowDetailedError** conmutador que aparece en el archivo Web.config bajo el \<appSettings\> nodo:</span><span class="sxs-lookup"><span data-stu-id="003ba-108">The following XML code shows the **ThrowDetailedError** switch that appears in the Web.config file under the \<appSettings\> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="003ba-109">BizTalk Server no devuelve información de excepción interior al cliente Web de forma predeterminada porque puede contener información confidencial, como pilas de llamadas de aplicación.</span><span class="sxs-lookup"><span data-stu-id="003ba-109">BizTalk Server does not return inner exception information to the Web client by default since it may contain sensitive information, such as application call stacks.</span></span> <span data-ttu-id="003ba-110">Tras la depuración, debe establecer el **ThrowDetailedError** si se establece en **False**.</span><span class="sxs-lookup"><span data-stu-id="003ba-110">After debugging, you should set the **ThrowDetailedError** setting to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003ba-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="003ba-111">See Also</span></span>  
 [<span data-ttu-id="003ba-112">Depuración de servicios web publicados</span><span class="sxs-lookup"><span data-stu-id="003ba-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)