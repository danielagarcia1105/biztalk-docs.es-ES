---
title: Copia de seguridad de aplicaciones de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b51e3ae6-08ed-48ca-8977-13f46144a5fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d125a1430aa2d044abba7632fa31a9c89f2bc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230380"
---
# <a name="backing-up-biztalk-server-applications"></a><span data-ttu-id="d7dc9-102">Realizar una copia de seguridad de aplicaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d7dc9-102">Backing Up BizTalk Server Applications</span></span>
<span data-ttu-id="d7dc9-103">Para asegurarse de que podrá recuperar el sistema de BizTalk Server después de que se haya producido un error de hardware, es importante contar con buenas copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-103">To ensure that you can recover your BizTalk Server system after a hardware failure, it is important to have good backups.</span></span> <span data-ttu-id="d7dc9-104">Para mantener las copias de seguridad, se aconseja exportar las aplicaciones de BizTalk a un servidor remoto y realizar una copia de seguridad de esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-104">As a part of keeping backups, it is a good idea to export your BizTalk applications to a remote server and to back up these applications.</span></span>  
  
 <span data-ttu-id="d7dc9-105">Más tarde, cuando restaure las bases de datos de BizTalk Server y vuelva a instalar BizTalk Server, podrá importar estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-105">Later, when you restore the BizTalk Server databases and reinstall BizTalk Server, you can import these applications.</span></span> <span data-ttu-id="d7dc9-106">Para obtener más información acerca de cómo exportar e importar aplicaciones, consulte [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc9-106">For more information about how to export and import applications, see [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="d7dc9-107">Debería exportar los archivos .msi de todas las aplicaciones BizTalk que se han implementado en el equipo y guardarlos en la ubicación de copias de seguridad (en un servidor distinto).</span><span class="sxs-lookup"><span data-stu-id="d7dc9-107">For all BizTalk applications deployed on the computer, you should export the .msi files and save them in your backup location (on a different server).</span></span> <span data-ttu-id="d7dc9-108">Los archivos .msi permiten volver a instalar los recursos que requiere BizTalk Server una vez que se ha recuperado el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-108">The .msi files enable you to reinstall the resources required by BizTalk Server after you recover the destination computer.</span></span> <span data-ttu-id="d7dc9-109">Debería asegurarse de que los archivos .msi incluyen todos los recursos necesarios y de que se especifican las acciones que se van a realizar en la instalación de los archivos .msi para estos recursos.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-109">You should ensure that the .msi files include all of the required resources, and that you specify the actions to be performed on the .msi installation for these resources.</span></span> <span data-ttu-id="d7dc9-110">Si la aplicación de BizTalk depende de cualquier ensamblado de usuario o de otros DLL que no están incluidos en los archivos .msi, se deben realizar copias de seguridad de ellos por separado.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-110">If your BizTalk application depends on any user assemblies or other DLLs that are not included in the .msi files, you must back up them up separately.</span></span>  
  
 <span data-ttu-id="d7dc9-111">El proceso de exportación de la aplicación es el mismo para los escenarios de enrutamiento por contenidos que para los que tienen orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-111">The application export process is the same for content-based routing scenarios as well as scenarios that have orchestrations.</span></span> <span data-ttu-id="d7dc9-112">Este proceso se debería repetir siempre que se cambien las aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d7dc9-112">You should repeat this process whenever you change the BizTalk applications.</span></span> <span data-ttu-id="d7dc9-113">Para obtener más información, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc9-113">For more information, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dc9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7dc9-114">See Also</span></span>  
 [<span data-ttu-id="d7dc9-115">Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d7dc9-115">Backing Up a Computer Running BizTalk Server</span></span>](../core/backing-up-a-computer-running-biztalk-server.md)