---
title: Seguridad de Windows SharePoint Services | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, Windows SharePoint Services
- Windows SharePoint Services, security
- security, BAS
- BAS, security
ms.assetid: ada6abd3-b867-49a6-8ee0-1466adc87dc5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184f5a237f796eac69de6c481e69a87a4a5358df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-security"></a><span data-ttu-id="56e3f-102">Seguridad de Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="56e3f-102">Windows SharePoint Services Security</span></span>
<span data-ttu-id="56e3f-103">Windows SharePoint Services 3.0 usa grupos de sitio de Windows SharePoint Services para administrar la seguridad de todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="56e3f-103">Windows SharePoint Services 3.0 uses Windows SharePoint Services site groups to manage site-wide security.</span></span> <span data-ttu-id="56e3f-104">Cada grupo de sitio posee los derechos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="56e3f-104">Each site group possesses corresponding rights.</span></span> <span data-ttu-id="56e3f-105">Los derechos son acciones que los usuarios pueden realizar, como ver, editar y eliminar recursos de sitio.</span><span class="sxs-lookup"><span data-stu-id="56e3f-105">Rights are actions that users can perform—such as view, edit, and delete site resources.</span></span> <span data-ttu-id="56e3f-106">Los recursos incluyen listas de sitios, bibliotecas de documentos y administración de sitios.</span><span class="sxs-lookup"><span data-stu-id="56e3f-106">Resources include site lists, document libraries, and site administration.</span></span> <span data-ttu-id="56e3f-107">Para cada rol creado en el cliente Web de perfil debe definir un grupo de sitios de Windows SharePoint Services y asignar derechos según corresponda a cada recurso al que ese grupo tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="56e3f-107">For each role created in the Profile Web Client you need to define a Windows SharePoint Service site group and assign rights accordingly to each resource to which that group has access.</span></span>  
  
 <span data-ttu-id="56e3f-108">Para obtener más información acerca de la seguridad de WSS 3.0, consulte la Guía de evaluación de WSS 3.0 en [http://go.microsoft.com/fwlink/?LinkID=94370](http://go.microsoft.com/fwlink/?LinkID=94370).</span><span class="sxs-lookup"><span data-stu-id="56e3f-108">For more information about WSS 3.0 security, see the WSS 3.0 evaluation guide at [http://go.microsoft.com/fwlink/?LinkID=94370](http://go.microsoft.com/fwlink/?LinkID=94370).</span></span>  
  
 <span data-ttu-id="56e3f-109">Esta sección contiene:</span><span class="sxs-lookup"><span data-stu-id="56e3f-109">This section contains:</span></span>  
  
-   [<span data-ttu-id="56e3f-110">Configuración de los usuarios de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="56e3f-110">Configuring A4SWIFT Users</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-users.md)  
  
-   [<span data-ttu-id="56e3f-111">Configuración de grupos de sitio de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="56e3f-111">Configuring A4SWIFT Site Groups</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-a4swift-site-groups.md)  
  
-   [<span data-ttu-id="56e3f-112">Asignación de derechos</span><span class="sxs-lookup"><span data-stu-id="56e3f-112">Assigning Rights</span></span>](../../adapters-and-accelerators/accelerator-swift/assigning-rights.md)