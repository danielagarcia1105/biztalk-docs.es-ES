---
title: Generar XML o esquema en PeopleSoft | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- generating XML
- XML, generating
ms.assetid: adfe2936-0dc2-42d2-b26a-718f8cc57eff
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a7fbd164f7c0d380f6ee0c0fda59098203f7585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="12c9d-102">Generación de XML o esquema en PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="12c9d-102">Generating XML or Schema in PeopleSoft</span></span>
<span data-ttu-id="12c9d-103">En el procedimiento siguiente se describe cómo usar PeopleSoft Enterprise para crear un archivo XML y desencadenar un evento de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="12c9d-103">The following procedure describes how to use PeopleSoft Enterprise to create an XML file and trigger a PeopleSoft event.</span></span> <span data-ttu-id="12c9d-104">Para ello, se debe realizar un cambio en el entorno de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="12c9d-104">To do this, you change something in the PeopleSoft environment.</span></span> <span data-ttu-id="12c9d-105">El cambio activa el archivo XML, que se envía a la carpeta de archivos que estableció en la orquestación que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="12c9d-105">The change activates an XML file, which is sent to the file folder that you set in your orchestration to be monitored.</span></span> <span data-ttu-id="12c9d-106">Después, en BizTalk Server, se importa el XML y se genera un esquema.</span><span class="sxs-lookup"><span data-stu-id="12c9d-106">Later, in BizTalk Server, you import the XML and generate a schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12c9d-107">Cuando se asocia la ubicación al nodo MSEXTERNAL, cualquier cambio realizado en el valor de ubicación genera un documento XML, lo que desencadena un evento.</span><span class="sxs-lookup"><span data-stu-id="12c9d-107">When you associate the Location with the MSEXTERNAL node, any change made to Location Value generates an XML document—triggering an event.</span></span> <span data-ttu-id="12c9d-108">Después de dar de alta e iniciar la orquestación, puede navegar por las pantallas de PeopleSoft hasta la pantalla LOCATION.</span><span class="sxs-lookup"><span data-stu-id="12c9d-108">After enlisting and starting your orchestration, you can navigate through the PeopleSoft screens to the LOCATION screen.</span></span> <span data-ttu-id="12c9d-109">Si realiza un cambio para el valor de ubicación y lo guarda, aparece un XML correspondiente en el directorio \out.</span><span class="sxs-lookup"><span data-stu-id="12c9d-109">If you make a change to Location Value and save your change, a corresponding XML appears in your \out directory.</span></span>  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a><span data-ttu-id="12c9d-110">Para generar XML o esquemas en PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="12c9d-110">To generate XML or Schema in PeopleSoft</span></span>  
  
1.  <span data-ttu-id="12c9d-111">En la aplicación PeopleSoft, apunte a **configurar operaciones financieras**, seleccione **Supply Chain**, seleccione **definiciones comunes**, seleccione **ubicación**y, a continuación, seleccione **ubicación**.</span><span class="sxs-lookup"><span data-stu-id="12c9d-111">In the PeopleSoft application, point to **Set up Financials**, point to **Supply Chain**, point to **Common Definitions**, point to **Location**, and then select **Location**.</span></span>  
  
2.  <span data-ttu-id="12c9d-112">En el **ubicación** pantalla, escriba la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="12c9d-112">On the **Location** screen, enter the following information:</span></span>  
  
    -   <span data-ttu-id="12c9d-113">**Id. de conjunto:** escriba **recurso compartido**.</span><span class="sxs-lookup"><span data-stu-id="12c9d-113">**Set ID:** Enter **SHARE**.</span></span>  
  
    -   <span data-ttu-id="12c9d-114">**Código de ubicación:** escriba un código que empiece por `WKLOC`.</span><span class="sxs-lookup"><span data-stu-id="12c9d-114">**Location Code:** Enter a code that starts with `WKLOC`.</span></span>  
  
     ![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")  
  
3.  <span data-ttu-id="12c9d-115">Haga clic en **búsqueda**y, a continuación, haga clic en **corregir historial** para colocar la pantalla **editar** modo.</span><span class="sxs-lookup"><span data-stu-id="12c9d-115">Click **Search**, and then click **Correct History** to put the screen in **Edit** mode.</span></span>  
  
     ![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")  
  
4.  <span data-ttu-id="12c9d-116">Realiza un cambio en un campo en la pantalla y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="12c9d-116">Make a change to a field on the screen, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="12c9d-117">Seleccione **PeopleTools**, seleccione **Integration Broker**, seleccione **Monitor**y, a continuación, seleccione **Monitor Message**.</span><span class="sxs-lookup"><span data-stu-id="12c9d-117">Point to **PeopleTools**, point to **Integration Broker**, point to **Monitor**, and then select **Monitor Message**.</span></span>  
  
     ![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")  
  
6.  <span data-ttu-id="12c9d-118">Asegúrese de que **tipo de canal** es **instancia de mensaje**y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="12c9d-118">Make sure that **Channel Type** is **Message Instance**, and then click **Refresh**.</span></span>  
  
7.  <span data-ttu-id="12c9d-119">En el **realiza** columna, haga clic en el número.</span><span class="sxs-lookup"><span data-stu-id="12c9d-119">In the **Done** column, click the number.</span></span>  
  
8.  <span data-ttu-id="12c9d-120">Desplácese hasta la parte inferior de la lista y haga clic en el **detalles** crear vínculos en un **LOCATION_SYNC** mensaje.</span><span class="sxs-lookup"><span data-stu-id="12c9d-120">Scroll to the bottom of the list and click the **Details** link on a **LOCATION_SYNC** message.</span></span>  
  
     ![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")  
  
9. <span data-ttu-id="12c9d-121">Haga clic en **ver XML** en un **MSEXTERNAL** nodo.</span><span class="sxs-lookup"><span data-stu-id="12c9d-121">Click **View XML** on a **MSEXTERNAL** Node.</span></span>  
  
     ![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")  
  
     <span data-ttu-id="12c9d-122">Copie y pegue el contenido del XML en un archivo al que pueda obtener acceso el proyecto de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="12c9d-122">Copy and paste the contents of the XML into a file that can be accessed by your BizTalk Server project.</span></span>  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. <span data-ttu-id="12c9d-123">Recuerde la ubicación del archivo al que hace referencia en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="12c9d-123">Remember the location of the file;  you reference it in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c9d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="12c9d-124">See Also</span></span>  
 [<span data-ttu-id="12c9d-125">Apéndice B: utilizando la aplicación PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="12c9d-125">Appendix B: Using the PeopleSoft Application</span></span>](../core/appendix-b-using-the-peoplesoft-application.md)