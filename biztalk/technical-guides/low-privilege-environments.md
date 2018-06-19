---
title: Entornos con pocos privilegios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d43f363bd96dd8e3109a8ce21b9565fb43e5f9bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298300"
---
# <a name="low-privilege-environments"></a><span data-ttu-id="77b88-102">Entornos con pocos privilegios</span><span class="sxs-lookup"><span data-stu-id="77b88-102">Low-Privilege Environments</span></span>
<span data-ttu-id="77b88-103">Varios flujos de trabajo que se incluyen con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración requiere permisos elevados para realizar determinadas acciones.</span><span class="sxs-lookup"><span data-stu-id="77b88-103">Several workflows that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack require elevated permissions to perform certain actions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="77b88-104">Módulo de administración le permite realizar funciones básicas de supervisión en un entorno con pocos privilegios.</span><span class="sxs-lookup"><span data-stu-id="77b88-104"> Management Pack enables you to perform basic monitoring functionalities in a low privilege environment.</span></span> <span data-ttu-id="77b88-105">Hay dos funciones administrativas: el Administrador de BizTalk Server y el operador de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="77b88-105">There are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="77b88-106">El Administrador de BizTalk Server tiene una función de muchos privilegios, con acceso a los datos de configuración y de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="77b88-106">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="77b88-107">El Administrador de BizTalk Server puede realizar todas las tareas administrativas claves tales dar de alta e iniciar los artefactos.</span><span class="sxs-lookup"><span data-stu-id="77b88-107">The BizTalk Server Administrator can perform all key administrative tasks such enlisting and starting artifacts.</span></span> <span data-ttu-id="77b88-108">El Operador de BizTalk Server tiene una función de pocos privilegios, con acceso sólo para supervisar y solucionar problemas de acciones.</span><span class="sxs-lookup"><span data-stu-id="77b88-108">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="77b88-109">Para obtener más información, consulte [derechos de usuario mínimos de seguridad](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx).</span><span class="sxs-lookup"><span data-stu-id="77b88-109">For more information, see [Minimum Security User Rights](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx).</span></span>  
  
 <span data-ttu-id="77b88-110">Usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración:</span><span class="sxs-lookup"><span data-stu-id="77b88-110">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack:</span></span>  
  
-   <span data-ttu-id="77b88-111">Los miembros del grupo de operadores de BizTalk Server pueden realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="77b88-111">Members of the BizTalk Server Operators group can do the following:</span></span>  
  
    -   <span data-ttu-id="77b88-112">Supervisar BizTalk Server para errores, realizar consultas para detectar suspendido, configuración de la vista.</span><span class="sxs-lookup"><span data-stu-id="77b88-112">Monitor BizTalk Server for errors, query for suspended messages\instances, view configuration.</span></span>  
  
    -   <span data-ttu-id="77b88-113">Supervisar las instalaciones de BizTalk Server y los artefactos.</span><span class="sxs-lookup"><span data-stu-id="77b88-113">Monitor BizTalk Server installations and artifacts.</span></span>  
  
    -   <span data-ttu-id="77b88-114">Ver el estado del servicio y el flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="77b88-114">View service state and message flow.</span></span>  
  
    -   <span data-ttu-id="77b88-115">Iniciar o detener aplicaciones y artefactos, como orquestaciones, puertos de envío o grupos de puertos que se encuentran en un estado dada de alta.</span><span class="sxs-lookup"><span data-stu-id="77b88-115">Start or stop applications and artifacts such as orchestrations, send ports or send port groups that are in an enlisted state.</span></span>  
  
    -   <span data-ttu-id="77b88-116">Habilitar o deshabilitar ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="77b88-116">Enable or disable receive locations.</span></span> <span data-ttu-id="77b88-117">Los cambios no se hacen efectivos hasta el próximo intervalo de actualización de la caché de 60 segundos, que es el intervalo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="77b88-117">The changes do not take effect until the next cache refresh interval of 60 seconds, which is the default.</span></span> <span data-ttu-id="77b88-118">El intervalo de actualización de la caché se establece en el nivel de grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="77b88-118">The cache refresh interval is set at the BizTalk Server group level.</span></span>  
  
-   <span data-ttu-id="77b88-119">Los miembros del grupo de operadores de BizTalk Server no pueden realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="77b88-119">Members of the BizTalk Server Operators group cannot do the following:</span></span>  
  
    -   <span data-ttu-id="77b88-120">Modificar la configuración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="77b88-120">Modify the configuration for BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="77b88-121">Ver las propiedades de contexto del mensaje que estén clasificadas como información que se pueda identificar personalmente o los cuerpos de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="77b88-121">View message context properties classified as Personally Identifiable Information (PII) or message bodies.</span></span>  
  
    -   <span data-ttu-id="77b88-122">Modificar el transcurso del enrutamiento de mensajes, como la eliminación de suscripciones del sistema en ejecución o la agregación de suscripciones nuevas a éste, así como la capacidad para publicar mensajes en el tiempo de ejecución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="77b88-122">Modify the course of message routing, such as removing or adding new subscriptions to the running system, including the ability to publish messages into the BizTalk Server runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77b88-123">Para llevar a cabo todas las tareas de supervisión proporcionadas por el módulo de administración, como reiniciar el servicio BTSNTSvc.exe, debe ser miembro del grupo Administradores local en los servidores BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="77b88-123">To perform all monitoring tasks provided by the Management Pack such as restarting BTSNTSvc.exe service, you must be a member of the local Administrators group on the BizTalk Servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77b88-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="77b88-124">In this section</span></span>  
  
-   [<span data-ttu-id="77b88-125">Supervisión</span><span class="sxs-lookup"><span data-stu-id="77b88-125">Monitoring</span></span>](../technical-guides/monitoring.md)  
  
-   [<span data-ttu-id="77b88-126">Detecciones</span><span class="sxs-lookup"><span data-stu-id="77b88-126">Discoveries</span></span>](../technical-guides/discoveries.md)