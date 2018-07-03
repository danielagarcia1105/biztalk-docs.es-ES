---
title: 'Lista de comprobación: Archivar y purgar la base de datos de seguimiento de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59a162d56badd7df7f49ceadc6abc3832dd50806
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971021"
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a><span data-ttu-id="d901b-102">Lista de comprobación: Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d901b-102">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>

|<span data-ttu-id="d901b-103">Paso</span><span class="sxs-lookup"><span data-stu-id="d901b-103">Step</span></span>|<span data-ttu-id="d901b-104">Referencia</span><span class="sxs-lookup"><span data-stu-id="d901b-104">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="d901b-105">Lea la información general de archivo y purga para familiarizarse con el proceso de archivo y purga de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d901b-105">Read the Archiving and Purging overview to become more familiar with the process of archiving and purging tracking data.</span></span>|[<span data-ttu-id="d901b-106">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d901b-106">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="d901b-107">Aunque puede ejecutar el trabajo DTA Purge and Archive mediante sus credenciales de inicio de sesión, debería configurar el rol BTS_BACKUP_USERS con las credenciales del servidor SQL Server para ejecutar el trabajo DTA Purge and Archive.</span><span class="sxs-lookup"><span data-stu-id="d901b-107">Although you can run the DTA Purge and Archive job using your logon credentials, for added security, you should configure the BTS_BACKUP_USERS role with the necessary SQL Server credentials to run the DTA Purge and Archive job.</span></span> <span data-ttu-id="d901b-108">Esto ayuda a evitar elevación de privilegios.</span><span class="sxs-lookup"><span data-stu-id="d901b-108">This helps to prevent elevation of privileges.</span></span>|[<span data-ttu-id="d901b-109">Cómo configurar la función BTS_BACKUP_USERS para archivar y purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d901b-109">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|<span data-ttu-id="d901b-110">Configure el trabajo DTA Purge and Archive.</span><span class="sxs-lookup"><span data-stu-id="d901b-110">Configure the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="d901b-111">Cómo configurar el trabajo DTA Purge and Archive</span><span class="sxs-lookup"><span data-stu-id="d901b-111">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|<span data-ttu-id="d901b-112">Ejecute el trabajo DTA Purge and Archive, lo que archiva los datos en la base de datos de seguimiento de BizTalk (BizTalkDTADb) y purga los datos antiguos.</span><span class="sxs-lookup"><span data-stu-id="d901b-112">Run the DTA Purge and Archive job, which archives the data in your BizTalk Tracking (BizTalkDTADb) database and purges old data.</span></span>|[<span data-ttu-id="d901b-113">Cómo purgar datos de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d901b-113">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="d901b-114">Opcionalmente, puede purgar datos manualmente desde la base de datos de seguimiento de BizTalk (BizTalkDTADb) </span><span class="sxs-lookup"><span data-stu-id="d901b-114">Optionally, you can manually purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="d901b-115">Cómo purgar datos manualmente desde la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d901b-115">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="d901b-116">Habilite la validación automática de los datos archivados desde la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="d901b-116">Enable automatic validation of the archived data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="d901b-117">Cómo habilitar la validación automática de archivos</span><span class="sxs-lookup"><span data-stu-id="d901b-117">How to Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)|  
|<span data-ttu-id="d901b-118">Copie los mensajes sometidos a seguimiento en la base de datos de seguimiento BizTalk (BizTalkDTAdb).</span><span class="sxs-lookup"><span data-stu-id="d901b-118">Copy tracked messages into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="d901b-119">Esto resulta necesario para purgar datos mediante el trabajo DTA Purge and Archive.</span><span class="sxs-lookup"><span data-stu-id="d901b-119">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="d901b-120">Cómo copiar mensajes controlados en la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d901b-120">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  

## <a name="see-also"></a><span data-ttu-id="d901b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d901b-121">See Also</span></span>  
 [<span data-ttu-id="d901b-122">Archivar y purgar la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="d901b-122">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)