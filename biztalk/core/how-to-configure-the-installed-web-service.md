---
title: "Cómo configurar el servicio Web instalado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, configuring
- deploying, Web services
- Web services, deploying
ms.assetid: 5a281daa-9e1c-47b0-9002-66ea18ed6caf
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f54d5fd99bfa9f5a7440202848c4d43259d0a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-installed-web-service"></a><span data-ttu-id="2bf4c-102">Cómo configurar el servicio Web instalado</span><span class="sxs-lookup"><span data-stu-id="2bf4c-102">How to Configure the Installed Web Service</span></span>
<span data-ttu-id="2bf4c-103">Después de instalar los archivos del servicio Web, debe configurar BizTalk Server para recibir mensajes del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-103">After you install the Web service files, you must configure BizTalk Server to receive messages from the Web service.</span></span>  
  
### <a name="to-configure-the-web-service"></a><span data-ttu-id="2bf4c-104">Para configurar el servicio Web</span><span class="sxs-lookup"><span data-stu-id="2bf4c-104">To configure the Web service</span></span>  
  
1.  <span data-ttu-id="2bf4c-105">En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, haga clic en la aplicación que desea configurar el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-105">In BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then right-click the application that you want to configure the Web Service.</span></span>  
  
2.  <span data-ttu-id="2bf4c-106">Seleccione **importación**y, a continuación, haga clic en **enlaces**.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-106">Point to **Import**, and then click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="2bf4c-107">Seleccione el archivo BindingInfo.xml en la carpeta de distribución y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-107">Select the BindingInfo.xml file in the distribution folder, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="2bf4c-108">Inicie las orquestaciones y habilite las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-108">Start your orchestrations and enable receive locations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf4c-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bf4c-109">See Also</span></span>  
 <span data-ttu-id="2bf4c-110">[Cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md) </span><span class="sxs-lookup"><span data-stu-id="2bf4c-110">[How to Import Bindings into a BizTalk Application](../core/how-to-import-bindings-into-a-biztalk-application.md) </span></span>  
 [<span data-ttu-id="2bf4c-111">Implementar servicios Web publicados en un equipo que no tenga Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2bf4c-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)