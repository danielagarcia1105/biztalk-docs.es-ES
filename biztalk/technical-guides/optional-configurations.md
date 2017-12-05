---
title: Configuraciones opcionales | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f4b0b51-2cad-4cb5-b6cd-4db92bd199fa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b19646c9c83eff4a3171b4d25763a6b581d45b1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="optional-configurations"></a><span data-ttu-id="3dc40-102">Configuraciones opcionales</span><span class="sxs-lookup"><span data-stu-id="3dc40-102">Optional Configurations</span></span>
<span data-ttu-id="3dc40-103">Después de importar el módulo de administración de BizTalk Server, el panel de navegación del panel supervisión muestra los tipos de objeto que se detectan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3dc40-103">After you import the BizTalk Server Management Pack, the navigation pane of the Monitoring pane displays the object types that are discovered automatically.</span></span> <span data-ttu-id="3dc40-104">Para obtener una lista de tipos de objetos, consulte [objetos detecta el módulo de administración](../technical-guides/objects-the-management-pack-discovers.md) sección.</span><span class="sxs-lookup"><span data-stu-id="3dc40-104">For a list of object types, see [Objects the Management Pack Discovers](../technical-guides/objects-the-management-pack-discovers.md) section.</span></span> <span data-ttu-id="3dc40-105">Puede modificar la configuración predeterminada de detección de objetos detectados por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración.</span><span class="sxs-lookup"><span data-stu-id="3dc40-105">You can modify the default discovery configuration of objects discovered by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack.</span></span> <span data-ttu-id="3dc40-106">Utilice la característica de invalidaciones de Operations Manager 2007 R2/2012 para cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="3dc40-106">You use the overrides feature of Operations Manager 2007 R2/2012 to change configuration settings.</span></span>  
  
 <span data-ttu-id="3dc40-107">Para un tipo de objeto que no se detecta automáticamente, puede habilitar la configuración de detección automática en el **Authoring** panel en la consola del operador.</span><span class="sxs-lookup"><span data-stu-id="3dc40-107">For an object type that is not automatically discovered, you can enable setting for automatic discovery in the **Authoring** pane in the Operations Console.</span></span>  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a><span data-ttu-id="3dc40-108">Para usar una invalidación para cambiar la configuración para la detección automática</span><span class="sxs-lookup"><span data-stu-id="3dc40-108">To use an override to change the setting for automatic discovery</span></span>  
  
1.  <span data-ttu-id="3dc40-109">En el panel de creación, expanda **objetos del módulo de administración**y, a continuación, haga clic en **detecciones de objetos**.</span><span class="sxs-lookup"><span data-stu-id="3dc40-109">In the Authoring pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
2.  <span data-ttu-id="3dc40-110">En la barra de herramientas de Operations Manager, haga clic en **ámbito**y filtrar los objetos que aparecen en el panel de detalles para incluir sólo los objetos de servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3dc40-110">On the Operations Manager toolbar, click **Scope**, and filter the objects that appear in the details pane to include only BizTalk Server objects.</span></span>  
  
3.  <span data-ttu-id="3dc40-111">En el panel de detalles, haga clic en el tipo de objeto que desea cambiar la configuración de.</span><span class="sxs-lookup"><span data-stu-id="3dc40-111">In the details pane, click the object type you want to change the setting for.</span></span>  
  
4.  <span data-ttu-id="3dc40-112">En la barra de herramientas de Operations Manager, haga clic en **invalida**, haga clic en **invalidar la detección de objetos**y, a continuación, haga clic en **para todos los objetos de tipo:** \<  *nombre de tipo de objeto de*\>, **para un grupo, para un objeto de tipo específico:** \< *nombre de tipo de objeto de*\>, o  **Para todos los objetos de otro tipo**.</span><span class="sxs-lookup"><span data-stu-id="3dc40-112">On the Operations Manager toolbar, click **Overrides**, click **Override the Object Discovery**, and then click either **For all objects of type:** \<*name of object type*\>, **For a group, For a specific object of type:** \<*name of object type*\>, or **For all objects of another type**.</span></span>  
  
5.  <span data-ttu-id="3dc40-113">En el **propiedades de invalidación** cuadro de diálogo, haga clic en el **invalidar** cuadro para la **habilitado** parámetro que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="3dc40-113">In the **Override Properties** dialog box, click the **Override** box for the **Enabled** parameter you want to change.</span></span>  
  
6.  <span data-ttu-id="3dc40-114">En **módulo de administración**, haga clic en **New** para crear una versión no sellada del módulo de administración y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3dc40-114">Under **Management Pack**, click **New** to create an unsealed version of the Management Pack, and then click **OK**.</span></span>  
  
 <span data-ttu-id="3dc40-115">Después de cambiar la configuración de invalidación, el tipo de objeto se detectará automáticamente y aparecerá en el panel supervisión en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3dc40-115">After you change the override setting, the object type will be automatically discovered and will appear in the Monitoring pane under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3dc40-116">Para obtener información acerca de la configuración de invalidaciones, consulte [invalidaciones en Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=86870) (http://go.microsoft.com/fwlink/?LinkId=86870).</span><span class="sxs-lookup"><span data-stu-id="3dc40-116">For information about setting overrides, see [Overrides in Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=86870) (http://go.microsoft.com/fwlink/?LinkId=86870).</span></span>