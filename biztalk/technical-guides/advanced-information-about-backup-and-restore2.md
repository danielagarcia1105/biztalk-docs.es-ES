---
title: Información avanzada sobre copias de seguridad y Restore2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa6a3527-4889-40ae-aacb-b8ea75be0329
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d197d8b6990a8106d51aaf53976503a4c28480ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997029"
---
# <a name="advanced-information-about-backup-and-restore"></a><span data-ttu-id="f2827-102">Información avanzada acerca de la realización de copia de seguridad y de restauración</span><span class="sxs-lookup"><span data-stu-id="f2827-102">Advanced Information About Backup and Restore</span></span>
<span data-ttu-id="f2827-103">En estos temas describen la copia de seguridad y los procesos de restauración con más detallan y están diseñados para ser utilizada por usuarios avanzados con una explicación exhaustiva sobre [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2827-103">The topics listed here describe the backup and restore processes in more detail and are intended to be used by advanced users with a thorough understanding of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="f2827-104">Para obtener información acerca de la transacción marcada, copias de seguridad completas y registros, vea [transacciones marcadas, copias de seguridad completas y las copias de seguridad del registro](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span><span class="sxs-lookup"><span data-stu-id="f2827-104">For information about marked transaction, full backups, and logs, see [Marked Transactions, Full Backups, and Log Backups](http://go.microsoft.com/fwlink/?LinkId=151565) (http://go.microsoft.com/fwlink/?LinkId=151565).</span></span>  
  
- <span data-ttu-id="f2827-105">Para obtener información acerca de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros, vea [BizTalk Server del trasvase de registros](http://go.microsoft.com/fwlink/?LinkId=151566) (<http://go.microsoft.com/fwlink/?LinkId=151566>).</span><span class="sxs-lookup"><span data-stu-id="f2827-105">For information about [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping, see [BizTalk Server Log Shipping](http://go.microsoft.com/fwlink/?LinkId=151566) (<http://go.microsoft.com/fwlink/?LinkId=151566>).</span></span>  
  
- <span data-ttu-id="f2827-106">Para obtener información sobre la programación de copia de seguridad [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del trabajo, consulte [cómo programar el trabajo de copia de seguridad de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=151568) (<http://go.microsoft.com/fwlink/?LinkId=151568>).</span><span class="sxs-lookup"><span data-stu-id="f2827-106">For information about scheduling backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job, see [How to Schedule the Backup BizTalk Server Job](http://go.microsoft.com/fwlink/?LinkId=151568) (<http://go.microsoft.com/fwlink/?LinkId=151568>).</span></span>  
  
- <span data-ttu-id="f2827-107">Para obtener información acerca de seguridad de bases de datos personalizadas, consulte [cómo volver de bases de datos personalizadas](http://go.microsoft.com/fwlink/?LinkId=151569) (http://go.microsoft.com/fwlink/?LinkId=151569).</span><span class="sxs-lookup"><span data-stu-id="f2827-107">For information about backing up custom databases, see [How to Back Up Custom Databases](http://go.microsoft.com/fwlink/?LinkId=151569) (http://go.microsoft.com/fwlink/?LinkId=151569).</span></span>  
  
- <span data-ttu-id="f2827-108">Para obtener información acerca de cómo crear un servidor vinculado, vea [cómo crear un servidor vinculado](http://go.microsoft.com/fwlink/?LinkId=151570) (http://go.microsoft.com/fwlink/?LinkId=151570).</span><span class="sxs-lookup"><span data-stu-id="f2827-108">For information about creating a linked server, see [How to Create a Linked Server](http://go.microsoft.com/fwlink/?LinkId=151570) (http://go.microsoft.com/fwlink/?LinkId=151570).</span></span>  
  
- <span data-ttu-id="f2827-109">Para obtener información acerca de cómo ver el historial de copias de seguridad restauradas, consulte [ver el historial de restaurar las copias de seguridad](http://go.microsoft.com/fwlink/?LinkId=151572) (http://go.microsoft.com/fwlink/?LinkId=151572).</span><span class="sxs-lookup"><span data-stu-id="f2827-109">For information about viewing the history of restored backups, see [Viewing the History of Restored Backups](http://go.microsoft.com/fwlink/?LinkId=151572) (http://go.microsoft.com/fwlink/?LinkId=151572).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2827-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f2827-110">In This Section</span></span>  
  
-   [<span data-ttu-id="f2827-111">Trasvase de registros de BizTalk Server mediante una dirección IP y el nombre del clúster de Windows</span><span class="sxs-lookup"><span data-stu-id="f2827-111">BizTalk Server Log Shipping Using a Windows Cluster Name and IP Address</span></span>](../technical-guides/biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address.md)  
  
-   [<span data-ttu-id="f2827-112">Restauración de la producción desde una copia de seguridad semiactiva</span><span class="sxs-lookup"><span data-stu-id="f2827-112">Restoring Production from a Warm Backup</span></span>](../technical-guides/restoring-production-from-a-warm-backup.md)