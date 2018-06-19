---
title: Opciones de instalación de SSO estándar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, installing
ms.assetid: 59aeb503-f369-4145-8a3c-ab60e9ed31a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26441ca5d63ebdb4cba807173f7e7068ff846bdf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279156"
---
# <a name="standard-sso-installation-options"></a><span data-ttu-id="22f09-102">Opciones de instalación de SSO estándar</span><span class="sxs-lookup"><span data-stu-id="22f09-102">Standard SSO Installation Options</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="22f09-103"> aprovecha las funciones de inicio de sesión único (SSO) empresarial para almacenar credenciales de forma segura y habilitar escenarios de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="22f09-103"> leverages the Enterprise Single Sign-On (SSO) capabilities for securely storing credentials to enable single sign-on scenarios.</span></span>  
  
 <span data-ttu-id="22f09-104">Asimismo, BizTalk Server utiliza SSO para almacenar de forma segura datos de configuración personalizada de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="22f09-104">BizTalk Server also uses SSO to store custom configuration data of Adapters securely.</span></span> <span data-ttu-id="22f09-105">Para realizar esto, las características de tiempo de ejecución y de administración de BizTalk Server instalan SSO como una característica dependiente.</span><span class="sxs-lookup"><span data-stu-id="22f09-105">To do this, BizTalk Server runtime and administration features install SSO as a dependent feature.</span></span> <span data-ttu-id="22f09-106">La instalación predeterminada de BizTalk Server instala SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="22f09-106">The default installation of BizTalk Server installs Enterprise SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22f09-107">Cuando se instala el inicio de sesión único empresarial (componente Servidor), se debe realizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="22f09-107">When Enterprise Single Sign-on (Server component) is installed, configuration needs to be performed.</span></span> <span data-ttu-id="22f09-108">El primer paso para configurar un sistema de SSO es configurar el servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="22f09-108">The first step to set up an SSO System is to configure the master secret server.</span></span> <span data-ttu-id="22f09-109">Se recomienda configurar un servidor secreto principal independiente.</span><span class="sxs-lookup"><span data-stu-id="22f09-109">It is recommended to set up a stand-alone master secret server.</span></span> <span data-ttu-id="22f09-110">Esto sólo se puede hacer seleccionando el inicio de sesión único empresarial del árbol de función personalizado en el programa de instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="22f09-110">This can be done by only selecting Enterprise Single Sign-on from the custom feature tree in BizTalk Server setup.</span></span>  
>   
>  <span data-ttu-id="22f09-111">También se recomienda que todos los equipos que ejecuten el inicio de sesión único empresarial dispongan de un servicio de sincronización de tiempo.</span><span class="sxs-lookup"><span data-stu-id="22f09-111">We also recommend that any computer running Enterprise Single Sign-On have a time synchronization service running.</span></span> <span data-ttu-id="22f09-112">De esta manera se mantiene la hora del equipo en sincronización con el resto del sistema, lo que resulta necesario para que los servicios de compra de vales de SSO funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="22f09-112">This keeps the computer time in sync with the rest of the system, which is necessary for SSO ticketing services to function properly.</span></span>  
  
 <span data-ttu-id="22f09-113">**Lista de opciones de instalación**: ejecutar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="22f09-113">**List of installation options**: Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup program.</span></span> <span data-ttu-id="22f09-114">Seleccione **instalación personalizada**y, a continuación, seleccione la opción adecuada en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="22f09-114">Select **Custom Installation**, and then select the appropriate option from the following list:</span></span>  
  
-   <span data-ttu-id="22f09-115">**Administración de inicio de sesión único de Enterprise:** herramientas de administración y el cliente para la asignación y conectarse a servicios de inicio de sesión único de empresa.</span><span class="sxs-lookup"><span data-stu-id="22f09-115">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
-   <span data-ttu-id="22f09-116">**Enterprise Single Sign-On servidor secreto principal:** actúa como el servidor secreto principal en el sistema SSO.</span><span class="sxs-lookup"><span data-stu-id="22f09-116">**Enterprise Single Sign-On Master Secret Server ―** Acts as the Master Secret Server in the SSO System.</span></span> <span data-ttu-id="22f09-117">Éste es el primer servidor del sistema de SSO que es necesario implementar y le permite crear la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="22f09-117">This is the first server in the SSO System that needs to deployed and this allows you to create the SSO database.</span></span>  
  
 <span data-ttu-id="22f09-118">Tras la instalación, también se podrán agregar los siguientes elementos mediante la utilidad Agregar o quitar programas:</span><span class="sxs-lookup"><span data-stu-id="22f09-118">You can also add the following after setup, by using the Add or Remove Programs utility:</span></span>  
  
-   <span data-ttu-id="22f09-119">**Servidor en tiempo de ejecución:** principales servicios para habilitar el inicio de sesión único y almacén ni acceder a datos de configuración de forma segura.</span><span class="sxs-lookup"><span data-stu-id="22f09-119">**Server Runtime ―** Core services to enable single sign-on and to store/access configuration data securely.</span></span>  
  
-   <span data-ttu-id="22f09-120">**Administración de inicio de sesión único de Enterprise:** herramientas de administración y el cliente para la asignación y conectarse a servicios de inicio de sesión único de empresa.</span><span class="sxs-lookup"><span data-stu-id="22f09-120">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
-   <span data-ttu-id="22f09-121">**Single Sign-On servicios empresariales con sincronización de contraseña:** servicios para habilitar la característica de sincronización de contraseña en el sistema de SSO empresarial.</span><span class="sxs-lookup"><span data-stu-id="22f09-121">**Enterprise Single Sign-On Services with Password Synchronization ―** Services to enable the Password Synchronization feature in the Enterprise SSO System.</span></span> <span data-ttu-id="22f09-122">Estos servicios también se integran con el Servicio de notificación de cambio de contraseña de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22f09-122">These services also integrate with the Microsoft Password Change Notification Service.</span></span> <span data-ttu-id="22f09-123">Después de haber instalado los servicios básicos de inicio de sesión único empresarial, puede instalar la característica Sincronización de contraseñas de SSO empresarial del paquete de BizTalk Server al iniciar \Platform\SSO\Setup.exe y seleccionar la característica Sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="22f09-123">Once you have installed the core Enterprise Single Sign-On services, you can install the Password Synchronization feature of Enterprise SSO from the BizTalk Server package by launching the \Platform\SSO\Setup.exe and selecting the Password Synchronization feature.</span></span>  
  
-   <span data-ttu-id="22f09-124">**Kit de desarrollo de software** programación e información de referencia.</span><span class="sxs-lookup"><span data-stu-id="22f09-124">**Software Development Kit** Programming and Reference information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22f09-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="22f09-125">In This Section</span></span>  
  
-   [<span data-ttu-id="22f09-126">Cómo instalar el componente de administración de SSO</span><span class="sxs-lookup"><span data-stu-id="22f09-126">How to Install the SSO Administration Component</span></span>](../core/how-to-install-the-sso-administration-component.md)  
  
-   [<span data-ttu-id="22f09-127">Cómo instalar la utilidad de cliente SSO</span><span class="sxs-lookup"><span data-stu-id="22f09-127">How to Install the SSO Client Utility</span></span>](../core/how-to-install-the-sso-client-utility.md)