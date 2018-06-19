---
title: Administración de programación del adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38563b3c-6d52-4e4e-ac6e-74f46ce22c6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b19e3285357bb067614aae9472eb099470fe27f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229812"
---
# <a name="adapter-programming-administration"></a><span data-ttu-id="07e95-102">Administración de programación del adaptador</span><span class="sxs-lookup"><span data-stu-id="07e95-102">Adapter Programming Administration</span></span>
<span data-ttu-id="07e95-103">Un adaptador es un tipo especial de aplicación de almacenamiento de configuración: es decir, un adaptador es un componente que comparte un espacio de nombres con otros Single Sign-On y aplicaciones de almacén de configuración.</span><span class="sxs-lookup"><span data-stu-id="07e95-103">An adapter is a special type of configuration store application: that is, an adapter is a component that shares a namespace with other Single Sign-On and configuration store applications.</span></span> <span data-ttu-id="07e95-104">Por lo tanto, puede tener acceso a información sobre un adaptador mediante ISSOConfigStore.</span><span class="sxs-lookup"><span data-stu-id="07e95-104">Therefore, you can access information about an adapter using ISSOConfigStore.</span></span> <span data-ttu-id="07e95-105">Sin embargo, a diferencia de la aplicación de almacenamiento de configuración, con la interfaz ISSOAdmin no realiza funciones administrativas en un adaptador.</span><span class="sxs-lookup"><span data-stu-id="07e95-105">But unlike a configuration store application, you do not perform administrative functions on an adapter with the ISSOAdmin interface.</span></span> <span data-ttu-id="07e95-106">En lugar de ello, administra un adaptador mediante ISSOPSAdmin.</span><span class="sxs-lookup"><span data-stu-id="07e95-106">Instead, you administer an adapter through ISSOPSAdmin.</span></span> <span data-ttu-id="07e95-107">La razón de una interfaz de administración de un adaptador especializado es que el sistema pueda coordinar otras actividades con el almacenamiento de configuración.</span><span class="sxs-lookup"><span data-stu-id="07e95-107">The reason for a specialized adapter administration interface is so that the system can coordinate other activities with the configuration store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e95-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="07e95-108">See Also</span></span>  
 <span data-ttu-id="07e95-109">[Configuración de programación del adaptador](../core/adapter-programming-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="07e95-109">[Adapter Programming Configuration](../core/adapter-programming-configuration.md) </span></span>  
 <span data-ttu-id="07e95-110">[Grupos de adaptadores y adaptadores de grupo](../core/adapter-groups-and-group-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="07e95-110">[Adapter Groups and Group Adapters](../core/adapter-groups-and-group-adapters.md) </span></span>  
 [<span data-ttu-id="07e95-111">Adaptadores de sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="07e95-111">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)