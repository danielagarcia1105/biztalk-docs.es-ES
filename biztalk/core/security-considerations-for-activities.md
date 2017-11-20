---
title: Consideraciones de seguridad para las actividades | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc49afd-a1c3-4ac7-8b89-11be667221e2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ea453b24ac3e8df25e7a4da98f27731f3828be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-activities"></a><span data-ttu-id="f5ed6-102">Consideraciones de seguridad para las actividades</span><span class="sxs-lookup"><span data-stu-id="f5ed6-102">Security Considerations for Activities</span></span>
<span data-ttu-id="f5ed6-103">Las funciones de seguridad que usa al interceptar el adaptador de WCF son las mismas que las usadas para las demás soluciones de BAM.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-103">The security roles you use when intercepting the WCF adapter are the same as those used for other BAM solutions.</span></span> <span data-ttu-id="f5ed6-104">Las consideraciones adicionales para la interceptación del adaptador de WCF conllevan la selección del usuario correcto y de qué función de escritor de eventos usar.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-104">The additional considerations for intercepting the WCF adapter involve selecting the correct user and event writer role to use.</span></span>  
  
 <span data-ttu-id="f5ed6-105">Al usar los servicios WCF y el adaptador de WCF, la función seleccionada escribe todos los datos relacionados con BAM en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-105">When using WCF services and the WCF adapter, all BAM-related data is written to the BAM Primary Import database by the selected role.</span></span>  
  
 <span data-ttu-id="f5ed6-106">Puede seleccionar la configuración de función de usuario adecuada evaluando su escenario de solución:</span><span class="sxs-lookup"><span data-stu-id="f5ed6-106">You can select the proper user role configuration by assessing your solution scenario:</span></span>  
  
-   <span data-ttu-id="f5ed6-107">Si su solución requiere muchos servicios nuevos de los que muy diversas actividades realizan un seguimiento, y todos se ejecutan bajo la misma cuenta de usuario, se recomienda usar la superfunción BAM_EVENT_WRITER para escribir los eventos interceptados.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-107">If your solution requires many new services that are tracked by many different activities, and are all run under the same user account, it is advantageous to use the BAM_EVENT_WRITER super role to write the intercepted events.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f5ed6-108">Los usuarios deben agregarse a la superfunción de escritor de eventos de BAM.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-108">Users must be added to the BAM event writer super role.</span></span> <span data-ttu-id="f5ed6-109">Al agregar un usuario a la superfunción, es importante recordar que este usuario podrá escribir en todas las actividades del sistema.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-109">When adding a user to the super role it is important to remember that the user will then be able to write to all the activities in the system.</span></span>  
  
-   <span data-ttu-id="f5ed6-110">Si su solución requiere un mayor control de los eventos escritos, deberá usar las funciones específicas de las actividades.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-110">If your solution requires greater control of the events written, then you should use activity-specific roles.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f5ed6-111">Los usuarios deben agregarse a la función de escritor de eventos específica de la actividad en concreto.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-111">Users must be added to the activity specific event writer role for each activity.</span></span>  
  
 <span data-ttu-id="f5ed6-112">Para obtener más información acerca de cómo configurar los roles de sistema de escritura de eventos BAM, consulte [cómo determinar y establecer Roles de escritor de eventos para las actividades](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).</span><span class="sxs-lookup"><span data-stu-id="f5ed6-112">For more information about configuring the BAM event writer roles, see [How to Determine and Set Event Writer Roles for Activities](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5ed6-113">Debe ser miembro del grupo Usuarios de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-113">You must be a member of the BizTalk Application Users group.</span></span>  
  
 <span data-ttu-id="f5ed6-114">Al seleccionar qué cuenta de usuario usar en la configuración del interceptor de WCF de BAM para la seguridad para la suplantación de IIS, debe tener en cuenta los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="f5ed6-114">When selecting the user account to use when configuring the BAM WCF interceptor for impersonation security under IIS you should consider the following scenarios:</span></span>  
  
-   <span data-ttu-id="f5ed6-115">Hospeda a sí mismo: Un ejecutable que se ejecute en el equipo que alberga el servicio WCF abierto.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-115">Self-Hosted: An executable running on your computer that holds the WCF service open.</span></span>  
  
-   <span data-ttu-id="f5ed6-116">Adaptador de WCF: las soluciones creadas con la **Asistente de publicación de servicio de WCF de Biztalk**.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-116">WCF adapter: Solutions created using the **Biztalk WCF Service Publishing Wizard**.</span></span>  
  
-   <span data-ttu-id="f5ed6-117">Hospedado en IIS: una solución alojada en una aplicación de IIS utilizando un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-117">IIS hosted: A solution hosted in an IIS application using a WCF Service.</span></span>  
  
 <span data-ttu-id="f5ed6-118">Use la siguiente tabla para facilitar la identificación de qué cuenta usar:</span><span class="sxs-lookup"><span data-stu-id="f5ed6-118">Use the following table to help identify the account to use:</span></span>  
  
|<span data-ttu-id="f5ed6-119">Tipo de solución</span><span class="sxs-lookup"><span data-stu-id="f5ed6-119">Solution type</span></span>|<span data-ttu-id="f5ed6-120">Cuenta que usar</span><span class="sxs-lookup"><span data-stu-id="f5ed6-120">Account to use</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="f5ed6-121">Con alojamiento propio</span><span class="sxs-lookup"><span data-stu-id="f5ed6-121">Self-hosted</span></span>|<span data-ttu-id="f5ed6-122">La cuenta que se usa para ejecutar el ejecutable que contendrá el servicio abierto.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-122">The account that is used to run the executable that will hold the service open.</span></span>|  
|<span data-ttu-id="f5ed6-123">Adaptador de WCF</span><span class="sxs-lookup"><span data-stu-id="f5ed6-123">WCF adapter</span></span>|<span data-ttu-id="f5ed6-124">Use la identidad AppPool: se trata de la instancia de AppPool asociada con el Vroot que aloja la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-124">Use the AppPool identity: This is the AppPool associated with the Vroot that houses the receive location.</span></span> <span data-ttu-id="f5ed6-125">Esta identidad se crea automáticamente cuando se usa el **Asistente de publicación de servicio de WCF de BizTalk** para publicar el sitio.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-125">This identity is created automatically when you use the **BizTalk WCF Service Publishing Wizard** to publish the site.</span></span> <span data-ttu-id="f5ed6-126">Puede considerar esto como un caso especial de la solución alojada en IIS.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-126">You can consider this a special case of the IIS-hosted solution.</span></span>|  
|<span data-ttu-id="f5ed6-127">Alojado en IIS</span><span class="sxs-lookup"><span data-stu-id="f5ed6-127">IIS-hosted</span></span>|<span data-ttu-id="f5ed6-128">La identidad del usuario AppPool que ejecuta la aplicación o VRoot del Servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f5ed6-128">The identity of the AppPool user running the WCF service VRoot/Application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5ed6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5ed6-129">See Also</span></span>  
 [<span data-ttu-id="f5ed6-130">Consideraciones de seguridad para los interceptores de BAM</span><span class="sxs-lookup"><span data-stu-id="f5ed6-130">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)