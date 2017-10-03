---
title: "Cómo actualizar la cadena de conexión para el libro de datos en directo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d2702fb-637c-46db-8b62-08ae15f983ba
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60de5d1ae904bdefffcf490e3a39d000b28a341d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a><span data-ttu-id="59258-102">Cómo actualizar la cadena de conexión del libro de trabajo de datos activos</span><span class="sxs-lookup"><span data-stu-id="59258-102">How to Update the Connection String for the Live Data Workbook</span></span>
<span data-ttu-id="59258-103">Cuando mueve la base de datos de importación principal de BAM a otro servidor, la cadena de conexión de un libro de trabajo de datos activos de BAM se debe actualizar para señalar al nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="59258-103">When you move the BAM Primary Import database to another server, the connection string in a BAM live data workbook must be updated to point to the new server.</span></span> <span data-ttu-id="59258-104">Se utiliza el complemento de BAM para Excel para realizar esta actualización.</span><span class="sxs-lookup"><span data-stu-id="59258-104">You use the BAM Add-in for Excel to make this update.</span></span>  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a><span data-ttu-id="59258-105">Para actualizar el libro de trabajo de datos activos para que señale a un servidor nuevo</span><span class="sxs-lookup"><span data-stu-id="59258-105">To update the live data workbook to point to a new server</span></span>  
  
1.  <span data-ttu-id="59258-106">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office**y, a continuación, haga clic en **Microsoft Office Excel**.</span><span class="sxs-lookup"><span data-stu-id="59258-106">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="59258-107">Haga clic en el **archivo** menú y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="59258-107">Click the **File** menu, and then click **Open**.</span></span> <span data-ttu-id="59258-108">Desplácese hasta el libro de trabajo de datos activos de BAM y haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="59258-108">Navigate to your BAM lived data workbook and click **Open**.</span></span>  
  
3.  <span data-ttu-id="59258-109">Haga clic en el **BAM** menú en el **Add-Ins** ficha y, a continuación, haga clic en **conexión de base de datos de BAM** para abrir el **Seleccionar base de datos de BAM** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="59258-109">Click the **BAM** menu in the **Add-Ins** tab, and then click **BAM DB Connection** to open the **Select BAM Database** dialog box.</span></span>  
  
4.  <span data-ttu-id="59258-110">En el **SQL Server** cuadro de texto, escriba el nombre de SQL server en el que la importación principal de BAM de base de datos ahora reside.</span><span class="sxs-lookup"><span data-stu-id="59258-110">In the **SQL Server** text box, type the name of the SQL server on which the BAM Primary Import database now resides.</span></span>  
  
5.  <span data-ttu-id="59258-111">Seleccione la base de datos de importación principal de BAM desde el **nombre de base de datos** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="59258-111">Select the BAM Primary Import database from the **Database Name** drop-down list.</span></span>  
  
6.  <span data-ttu-id="59258-112">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="59258-112">Click **OK** to close the dialog box.</span></span>  
  
7.  <span data-ttu-id="59258-113">Guarde el libro de trabajo.</span><span class="sxs-lookup"><span data-stu-id="59258-113">Save the workbook.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59258-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="59258-114">See Also</span></span>  
 <span data-ttu-id="59258-115">[Administración de BAM](../core/managing-bam.md) </span><span class="sxs-lookup"><span data-stu-id="59258-115">[Managing BAM](../core/managing-bam.md) </span></span>  
 [<span data-ttu-id="59258-116">Requisitos para usar el complemento de BAM para Excel</span><span class="sxs-lookup"><span data-stu-id="59258-116">Requirements for Using the BAM Add-In for Excel</span></span>](../core/requirements-for-using-the-bam-add-in-for-excel.md)