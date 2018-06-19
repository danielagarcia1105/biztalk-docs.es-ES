---
title: Cómo configurar Windows SharePoint Services envían controlador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], send handlers
- send handlers, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, send handlers
ms.assetid: 457767d9-6e39-4553-9bbe-212fcb7c04bc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8e110fb2a671fc839fb96cfdc2ad03169649e6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969138"
---
# <a name="how-to-configure-a-windows-sharepoint-services-send-handler"></a><span data-ttu-id="05d5a-102">Cómo configurar un controlador de envío de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="05d5a-102">How to Configure a Windows SharePoint Services Send Handler</span></span>
<span data-ttu-id="05d5a-103">Siga el procedimiento siguiente para modificar el host al que está asociado el controlador de recepción de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="05d5a-103">Use the following procedure to change the host with which the Windows SharePoint Services send handler is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05d5a-104">Cada host puede tener solo un controlador de envío asociado a él.</span><span class="sxs-lookup"><span data-stu-id="05d5a-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-a-windows-sharepoint-services-send-handler"></a><span data-ttu-id="05d5a-105">Para cambiar variables globales para un controlador de envío de Windows SharePoint Services.</span><span class="sxs-lookup"><span data-stu-id="05d5a-105">To change global variables for a Windows SharePoint Services send handler</span></span>  
  
1.  <span data-ttu-id="05d5a-106">En la consola de administración de BizTalk Server, haga clic para expandir [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**y, a continuación, haga clic para expandir **grupo de BizTalk [\<servername\>:\< base de datos de administración\>]**, haga clic para expandir **configuración de plataforma**y, a continuación, haga clic para expandir **adaptadores**.</span><span class="sxs-lookup"><span data-stu-id="05d5a-106">In the BizTalk Server Administration console, click to expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, and then click to expand **BizTalk Group [\<servername\>:\<management database\>]**, click to expand **Platform Settings**, and then click to expand **Adapters**.</span></span> <span data-ttu-id="05d5a-107">La lista de adaptadores aparece debajo de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="05d5a-107">The list of adapters appears under the folder.</span></span>  
  
2.  <span data-ttu-id="05d5a-108">Haga clic en **Windows SharePoint Services**y en el panel derecho, haga clic en el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="05d5a-108">Click **Windows SharePoint Services**, and in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="05d5a-109">En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="05d5a-109">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  
  
4.  <span data-ttu-id="05d5a-110">En el **General** , haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="05d5a-110">On the **General** tab, click **Properties**.</span></span>  
  
5.  <span data-ttu-id="05d5a-111">En el **propiedades de transporte de Windows SharePoint Services** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="05d5a-111">In the **Windows SharePoint Services Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="05d5a-112">Use</span><span class="sxs-lookup"><span data-stu-id="05d5a-112">Use this</span></span>|<span data-ttu-id="05d5a-113">Para</span><span class="sxs-lookup"><span data-stu-id="05d5a-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="05d5a-114">Tamaño del lote de envío</span><span class="sxs-lookup"><span data-stu-id="05d5a-114">Send Batch Size</span></span>|<span data-ttu-id="05d5a-115">Número máximo de documentos que procesará el servicio Web del adaptador de mensajería de Windows SharePoint Services por lotes.</span><span class="sxs-lookup"><span data-stu-id="05d5a-115">The maximum number of documents that the Windows SharePoint Services Web service will process as a batch.</span></span> <span data-ttu-id="05d5a-116">El valor predeterminado es 20.</span><span class="sxs-lookup"><span data-stu-id="05d5a-116">The default is 20.</span></span> <span data-ttu-id="05d5a-117">**Nota:** el valor mínimo es 1.</span><span class="sxs-lookup"><span data-stu-id="05d5a-117">**Note:**  The minimum value is 1.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05d5a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="05d5a-118">See Also</span></span>  
 <span data-ttu-id="05d5a-119">[Cómo configurar Windows SharePoint Services ubicación de recepción](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="05d5a-119">[How to Configure a Windows SharePoint Services Receive Location](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md) </span></span>  
 <span data-ttu-id="05d5a-120">[Cómo configurar un puerto de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="05d5a-120">[How to Configure a Windows SharePoint Services Send Port](../core/how-to-configure-a-windows-sharepoint-services-send-port.md) </span></span>  
 <span data-ttu-id="05d5a-121">[Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md) </span><span class="sxs-lookup"><span data-stu-id="05d5a-121">[How to Create a Send Port](../core/how-to-create-a-send-port2.md) </span></span>  
 <span data-ttu-id="05d5a-122">[Referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="05d5a-122">[Windows SharePoint Services Adapter Properties Reference](../core/windows-sharepoint-services-adapter-properties-reference.md) </span></span>  
 <span data-ttu-id="05d5a-123">[Expresiones del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="05d5a-123">[Windows SharePoint Services Adapter Expressions](../core/windows-sharepoint-services-adapter-expressions.md) </span></span>  
 [<span data-ttu-id="05d5a-124">Tipos de columna admitidos de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="05d5a-124">Supported Windows SharePoint Services Column Types</span></span>](../core/supported-windows-sharepoint-services-column-types.md)