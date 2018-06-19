---
title: Cómo hacer copia de seguridad la configuración del servidor de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f89050-c204-4d44-a875-299e690489ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad54aba8f8f49adeb8534bdbe28add15f0fe9638
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247660"
---
# <a name="how-to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="56270-102">Cómo efectuar una copia de seguridad de la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="56270-102">How to Back Up The BizTalk Server Configuration</span></span>
<span data-ttu-id="56270-103">Como parte de la creación de una copia de seguridad de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se debe realizar una copia de este tipo de los valores de configuración asociados con el equipo en el que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56270-103">As part of backing up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you should back up the configuration settings associated with the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="56270-104">En el caso de que se produzca un error de hardware que requiera la sustitución del equipo, el proceso de restauración se simplifica considerablemente si se dispone de una copia del archivo de configuración original.</span><span class="sxs-lookup"><span data-stu-id="56270-104">Having a copy of the original configuration file greatly simplifies the restoration process if you have a hardware failure that requires you to replace the computer.</span></span>  
  
 <span data-ttu-id="56270-105">El Administrador de configuración de BizTalk Server crea un archivo XML en el que se almacenan los valores de configuración de cada uno de los equipos en los que se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56270-105">The configuration settings for each computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are stored in an XML file created by the BizTalk Server Configuration Manager.</span></span> <span data-ttu-id="56270-106">Siempre que se cambie la configuración de los servidores BizTalk Server, se debe exportar el archivo de configuración a la ubicación de copia de seguridad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="56270-106">Any time you change the configuration of your BizTalk servers, you should export the updated configuration file to your backup location.</span></span> <span data-ttu-id="56270-107">Con esto, se contribuye a garantizar que el archivo de configuración se encuentre disponible en el caso de que resulte necesario reemplazar el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="56270-107">This helps to ensure that the configuration file is available if you have to replace your BizTalk server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="56270-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="56270-108">Prerequisites</span></span>  
 <span data-ttu-id="56270-109">Para llevar a cabo este procedimiento, debe haber iniciado la sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="56270-109">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-biztalk-server-configuration"></a><span data-ttu-id="56270-110">Para efectuar una copia de seguridad de la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="56270-110">To back up the BizTalk Server configuration</span></span>  
  
1.  <span data-ttu-id="56270-111">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft BizTalk Server**y, a continuación, haga clic en **configuración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="56270-111">Click **Start**, click **All Programs**, click **Microsoft BizTalk Server**, and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="56270-112">En **configuración de Microsoft BizTalk Server**, haga clic en **Exportar configuración**.</span><span class="sxs-lookup"><span data-stu-id="56270-112">In **Microsoft BizTalk Server Configuration**, click **Export Configuration**.</span></span>  
  
3.  <span data-ttu-id="56270-113">En el **Guardar como** cuadro de diálogo, vaya a la ubicación donde se almacenan las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="56270-113">In the **Save As** dialog box, browse to the location where you store your backups.</span></span>  
  
4.  <span data-ttu-id="56270-114">En el **nombre de archivo** , escriba un nombre para el archivo de configuración y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="56270-114">In the **File name** box, type a name for the configuration file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56270-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="56270-115">See Also</span></span>  
 <span data-ttu-id="56270-116">[Realizar una copia de seguridad de un equipo que ejecuta BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="56270-116">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="56270-117">Cómo recuperar la configuración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="56270-117">How to Recover the BizTalk Server Configuration</span></span>](../core/how-to-recover-the-biztalk-server-configuration.md)