---
title: "Contención de E/S de disco de archivos de supervisión y reducir el registro de DTC | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8b968dd-216e-454f-9224-aaf92ffd363b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7206c4220153ee95f78e5744a2df2ff7eeb3541e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a><span data-ttu-id="de45b-102">Supervisión y reducir la contención de E/S de disco del archivo de registro DTC</span><span class="sxs-lookup"><span data-stu-id="de45b-102">Monitoring and Reducing DTC Log File Disk I/O Contention</span></span>
<span data-ttu-id="de45b-103">El archivo de registro de coordinador de transacciones distribuidas (DTC) puede convertirse en un cuello de botella de E/S de disco en entornos con muchas transacciones.</span><span class="sxs-lookup"><span data-stu-id="de45b-103">The Distributed Transaction Coordinator (DTC) log file can become a disk I/O bottleneck in transaction-intensive environments.</span></span> <span data-ttu-id="de45b-104">Esto es especialmente cierto cuando se utiliza adaptadores que admiten transacciones, por ejemplo, SQL Server, MSMQ y MQSeries, o en un entorno de cuadro de mensajes múltiples.</span><span class="sxs-lookup"><span data-stu-id="de45b-104">This is especially true when using adapters that support transactions, such as SQL Server, MSMQ, or MQSeries, or in a multi-MessageBox environment.</span></span> <span data-ttu-id="de45b-105">Adaptadores transaccionales usen transacciones DTC y entornos de cuadro de mensajes múltiples hacen un amplio uso de transacciones DTC.</span><span class="sxs-lookup"><span data-stu-id="de45b-105">Transactional adapters use DTC transactions, and multi-MessageBox environments make extensive use of DTC transactions.</span></span>  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a><span data-ttu-id="de45b-106">Supervisar el uso en entornos en clúster y no clúster</span><span class="sxs-lookup"><span data-stu-id="de45b-106">Monitoring Usage in Clustered and Non-Clustered Environments</span></span>  
 <span data-ttu-id="de45b-107">Para asegurarse de que el archivo de registro DTC no se convierten en un cuello de botella de E/S de disco, debe supervisar el uso de E/S del disco donde reside el archivo de registro DTC en el servidor de base de datos de SQL Server de disco.</span><span class="sxs-lookup"><span data-stu-id="de45b-107">To ensure that the DTC log file does not become a disk I/O bottleneck, you should monitor the disk I/O usage for the disk where the DTC log file resides on the SQL Server database server.</span></span>  
  
 <span data-ttu-id="de45b-108">En un entorno donde está en el clúster de SQL Server, esto no es tanto un problema porque el archivo de registro ya estarán en una unidad compartida, que probablemente será una unidad de SAN rápida con varios ejes.</span><span class="sxs-lookup"><span data-stu-id="de45b-108">In an environment where SQL Server is clustered, this is not as much of a concern because the log file will already be on a shared drive, which will likely be a fast SAN drive with multiple spindles.</span></span> <span data-ttu-id="de45b-109">Sin embargo, todavía debe supervisar el uso de E/S de disco ya que puede convertirse en un cuello de botella en entornos no agrupado o si el archivo de registro DTC en un disco compartido con otros archivos de uso intensivo del disco.</span><span class="sxs-lookup"><span data-stu-id="de45b-109">You should nevertheless still monitor the disk I/O usage since it can become a bottleneck in non-clustered environments or when the DTC log file is on a shared disk with other disk-intensive files.</span></span>  
  
## <a name="troubleshooting-dtc"></a><span data-ttu-id="de45b-110">Solución de problemas de DTC</span><span class="sxs-lookup"><span data-stu-id="de45b-110">Troubleshooting DTC</span></span>  
 <span data-ttu-id="de45b-111">Para obtener información sobre solución de problemas de DTC, vea "Solucionar problemas con MSDTC" en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda en [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).</span><span class="sxs-lookup"><span data-stu-id="de45b-111">For information about troubleshooting DTC, see "Troubleshooting Problems with MSDTC" in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de45b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="de45b-112">See Also</span></span>  
 [<span data-ttu-id="de45b-113">Lista de comprobación: Configurar Windows Server</span><span class="sxs-lookup"><span data-stu-id="de45b-113">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)