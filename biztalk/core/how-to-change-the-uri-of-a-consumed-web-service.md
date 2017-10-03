---
title: "Cómo cambiar el URI de un servicio Web consumido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, modifying
- Web services, consuming
- consuming [Web services]
- modifying, Web services
ms.assetid: 907de565-8c99-4d34-939f-fd3dba37dd11
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9ae7d7178fc24c5f16b28325fb627045e5273a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a><span data-ttu-id="5a361-102">Cómo cambiar el URI de un servicio web consumido</span><span class="sxs-lookup"><span data-stu-id="5a361-102">How to Change the URI of a Consumed Web Service</span></span>
<span data-ttu-id="5a361-103">Después de implementar la orquestación, BizTalk Server configura un puerto de envío para cada servicio Web al que la orquestación hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5a361-103">After you deploy your orchestration, BizTalk Server configures a send port for each Web service that the orchestration references.</span></span> <span data-ttu-id="5a361-104">De forma predeterminada, BizTalk utiliza la URL del servicio Web en tiempo de ejecución para la misma URL para el servicio Web importado.</span><span class="sxs-lookup"><span data-stu-id="5a361-104">By default, BizTalk uses the URL of the Web service at run time for the same URL for the imported Web service.</span></span> <span data-ttu-id="5a361-105">Puede cambiar esta dirección URL mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5a361-105">You can change this URL using BizTalk Server Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a361-106">Debe implementar la orquestación antes de cambiar el URI de un servicio Web consumido.</span><span class="sxs-lookup"><span data-stu-id="5a361-106">You must deploy your orchestration before you change the URI of a consumed Web service.</span></span> <span data-ttu-id="5a361-107">Para obtener más información sobre la implementación de la orquestación, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="5a361-107">For more information on deploying your orchestration, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a><span data-ttu-id="5a361-108">Para cambiar el URI de un servicio Web consumido mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5a361-108">To change the URI of a consumed Web service using BizTalk Server Administration Console</span></span>  
  
1.  <span data-ttu-id="5a361-109">En la consola de administración de BizTalk Server, expanda una aplicación de BizTalk y, a continuación, expanda el **puertos de envío** nodo.</span><span class="sxs-lookup"><span data-stu-id="5a361-109">In BizTalk Server Administration console, expand a BizTalk application, and then expand the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="5a361-110">Haga clic en un puerto de envío configurado con el adaptador de SOAP, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5a361-110">Right-click a send port configured with SOAP adapter, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5a361-111">Si no tiene puertos físicos, puede crear puertos de envío y ubicaciones de recepción mediante la consola de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5a361-111">If you do not have physical ports, you can create send ports and receive locations by using BizTalk Administration console.</span></span> <span data-ttu-id="5a361-112">Para obtener información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).</span><span class="sxs-lookup"><span data-stu-id="5a361-112">For information, see [How to Create a Send Port](../core/how-to-create-a-send-port2.md).</span></span>  
  
4.  <span data-ttu-id="5a361-113">En el **enviar propiedades** cuadro de diálogo, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="5a361-113">On the **Send Properties** dialog box, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="5a361-114">En el **propiedades de transporte SOAP** cuadro de diálogo, en la **dirección URL del servicio Web** , escriba la dirección URL completa para la ubicación del servicio Web y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5a361-114">In the **SOAP Transport Properties** dialog box, in the **Web Service URL** box, type the full URL for the location of the Web service, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a361-115">Deberá asegurarse de que existe un servicio Web para la URL que especifique.</span><span class="sxs-lookup"><span data-stu-id="5a361-115">You should ensure that a Web service exists for the URL that you specify.</span></span> <span data-ttu-id="5a361-116">BizTalk Server no valida la ubicación de la URL.</span><span class="sxs-lookup"><span data-stu-id="5a361-116">BizTalk Server does not validate the URL location.</span></span>  
  
6.  <span data-ttu-id="5a361-117">Haga clic en Aceptar para salir del **propiedades de envío** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5a361-117">Click OK to exit the **Send Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a361-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a361-118">See Also</span></span>  
 <span data-ttu-id="5a361-119">[Uso de la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md) </span><span class="sxs-lookup"><span data-stu-id="5a361-119">[Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md) </span></span>  
 <span data-ttu-id="5a361-120">[Cómo configurar un puerto de envío de SOAP](../core/how-to-configure-a-soap-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="5a361-120">[How to Configure a SOAP Send Port](../core/how-to-configure-a-soap-send-port.md) </span></span>  
 <span data-ttu-id="5a361-121">[Encabezados SOAP con servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md) </span><span class="sxs-lookup"><span data-stu-id="5a361-121">[SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md) </span></span>  
 [<span data-ttu-id="5a361-122">Creación de puertos Web</span><span class="sxs-lookup"><span data-stu-id="5a361-122">Creating Web Ports</span></span>](../core/creating-web-ports.md)