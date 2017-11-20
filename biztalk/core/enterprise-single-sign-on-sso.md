---
title: Enterprise Single Sign-On (SSO) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6cbc5f514d13cd8457cd9417be5ea5b78408e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enterprise-single-sign-on-sso"></a><span data-ttu-id="df6ec-102">Inicio de sesión único (SSO) empresarial.</span><span class="sxs-lookup"><span data-stu-id="df6ec-102">Enterprise Single Sign-On (SSO)</span></span>
<span data-ttu-id="df6ec-103">El inicio de sesión único (SSO) empresarial proporciona servicios para almacenar y transmitir credenciales de usuario cifradas a través de los límites locales y de red, incluidos los límites de dominio.</span><span class="sxs-lookup"><span data-stu-id="df6ec-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="df6ec-104">SSO almacena las credenciales en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="df6ec-104">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="df6ec-105">Puesto que SSO proporciona una solución de inicio de sesión único (SSO) genérica, las aplicaciones de software intermedio y los adaptadores personalizados pueden aprovechar SSO para almacenar las credenciales de usuario y transmitirlas por el entorno de forma segura.</span><span class="sxs-lookup"><span data-stu-id="df6ec-105">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="df6ec-106">Los usuarios finales no necesitan recordar distintas credenciales para aplicaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="df6ec-106">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="df6ec-107">El sistema de inicio de sesión (SSO) se compone de una base de datos de SSO, un servidor secreto principal y uno o varios servidores de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="df6ec-107">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="df6ec-108">Contiene el sistema SSO *aplicaciones afiliadas* que define un administrador.</span><span class="sxs-lookup"><span data-stu-id="df6ec-108">The SSO system contains *affiliate applications* that an administrator defines.</span></span> <span data-ttu-id="df6ec-109">Un *aplicación afiliada* es una entidad lógica que representa un sistema o subsistema, como un host, el sistema back-end o la línea de aplicaciones empresariales para que se conecta mediante Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="df6ec-109">An *affiliate application* is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="df6ec-110">Cada aplicación afiliada tiene varias asignaciones de usuario; por ejemplo, tiene asignaciones establecidas entre las credenciales de un usuario en Active Directory y las credenciales de RACF correspondientes.</span><span class="sxs-lookup"><span data-stu-id="df6ec-110">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="df6ec-111">La base de datos de SSO es la base de datos de SQL Server que almacena la información acerca de las aplicaciones afiliadas, así como de todas las credenciales de usuario cifradas en todas las aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="df6ec-111">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all of the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="df6ec-112">El *servidor secreto principal* es el servidor de Enterprise Single Sign-On que almacena el secreto principal.</span><span class="sxs-lookup"><span data-stu-id="df6ec-112">The *master secret server* is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="df6ec-113">Todos los servidores de inicio de sesión único (SSO) del sistema obtienen el secreto principal del servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="df6ec-113">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="df6ec-114">El sistema SSO también contiene uno o más servidores de SSO.</span><span class="sxs-lookup"><span data-stu-id="df6ec-114">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="df6ec-115">Estos servidores llevan a cabo la asignación entre las credenciales de Microsoft Windows y el servidor, además de buscar las credenciales en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="df6ec-115">These servers do the mapping between the Microsoft Windows and back-end credentials, and look up the credentials in the SSO database.</span></span> <span data-ttu-id="df6ec-116">Los administradores los utilizan para el mantenimiento del sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="df6ec-116">Administrators use them to maintain the SSO system.</span></span>  
  
 <span data-ttu-id="df6ec-117">Para más obtener una visión completa en Enterprise Single Sign-On, vea [descripción SSO](../core/understanding-sso.md).</span><span class="sxs-lookup"><span data-stu-id="df6ec-117">For more a complete look at Enterprise Single Sign-On, see [Understanding SSO](../core/understanding-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df6ec-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="df6ec-118">See Also</span></span>  
 [<span data-ttu-id="df6ec-119">Arquitectura en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="df6ec-119">Runtime Architecture</span></span>](../core/runtime-architecture.md)