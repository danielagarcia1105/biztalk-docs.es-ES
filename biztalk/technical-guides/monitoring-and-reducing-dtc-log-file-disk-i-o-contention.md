---
title: Contención de E/S de disco de archivos de supervisión y reducir el registro de DTC | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8b968dd-216e-454f-9224-aaf92ffd363b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca71b55c2f9e18875ef67e840e8dac18a81dddac
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007421"
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a><span data-ttu-id="2ee72-102">Supervisión y reducir la contención de E/S de disco del archivo de registro DTC</span><span class="sxs-lookup"><span data-stu-id="2ee72-102">Monitoring and Reducing DTC Log File Disk I/O Contention</span></span>
<span data-ttu-id="2ee72-103">El archivo de registro de coordinador de transacciones distribuidas (DTC) puede convertirse en un cuello de botella de E/S de disco en entornos con muchas transacciones.</span><span class="sxs-lookup"><span data-stu-id="2ee72-103">The Distributed Transaction Coordinator (DTC) log file can become a disk I/O bottleneck in transaction-intensive environments.</span></span> <span data-ttu-id="2ee72-104">Esto es especialmente cierto cuando se utiliza adaptadores que admiten transacciones, por ejemplo, SQL Server, MSMQ y MQSeries, o en un entorno de cuadro de mensajes múltiples.</span><span class="sxs-lookup"><span data-stu-id="2ee72-104">This is especially true when using adapters that support transactions, such as SQL Server, MSMQ, or MQSeries, or in a multi-MessageBox environment.</span></span> <span data-ttu-id="2ee72-105">Adaptadores transaccionales usen transacciones DTC y entornos de cuadro de mensajes múltiples hacen un amplio uso de transacciones DTC.</span><span class="sxs-lookup"><span data-stu-id="2ee72-105">Transactional adapters use DTC transactions, and multi-MessageBox environments make extensive use of DTC transactions.</span></span>  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a><span data-ttu-id="2ee72-106">Supervisar el uso en entornos en clúster y no clúster</span><span class="sxs-lookup"><span data-stu-id="2ee72-106">Monitoring Usage in Clustered and Non-Clustered Environments</span></span>  
 <span data-ttu-id="2ee72-107">Para asegurarse de que el archivo de registro DTC no se convierten en un cuello de botella de E/S de disco, debe supervisar el uso de E/S del disco donde reside el archivo de registro DTC en el servidor de base de datos de SQL Server de disco.</span><span class="sxs-lookup"><span data-stu-id="2ee72-107">To ensure that the DTC log file does not become a disk I/O bottleneck, you should monitor the disk I/O usage for the disk where the DTC log file resides on the SQL Server database server.</span></span>  
  
 <span data-ttu-id="2ee72-108">En un entorno donde está en el clúster de SQL Server, esto no es tanto un problema porque el archivo de registro ya estarán en una unidad compartida, que probablemente será una unidad de SAN rápida con varios ejes.</span><span class="sxs-lookup"><span data-stu-id="2ee72-108">In an environment where SQL Server is clustered, this is not as much of a concern because the log file will already be on a shared drive, which will likely be a fast SAN drive with multiple spindles.</span></span> <span data-ttu-id="2ee72-109">Sin embargo, todavía debe supervisar el uso de E/S de disco ya que puede convertirse en un cuello de botella en entornos no agrupado o si el archivo de registro DTC en un disco compartido con otros archivos de uso intensivo del disco.</span><span class="sxs-lookup"><span data-stu-id="2ee72-109">You should nevertheless still monitor the disk I/O usage since it can become a bottleneck in non-clustered environments or when the DTC log file is on a shared disk with other disk-intensive files.</span></span>  
  
## <a name="troubleshooting-dtc"></a><span data-ttu-id="2ee72-110">Solución de problemas de DTC</span><span class="sxs-lookup"><span data-stu-id="2ee72-110">Troubleshooting DTC</span></span>  
 <span data-ttu-id="2ee72-111">Para obtener información sobre solución de problemas de DTC, vea "Solucionar problemas con MSDTC" en la Ayuda de BizTalk Server en [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).</span><span class="sxs-lookup"><span data-stu-id="2ee72-111">For information about troubleshooting DTC, see "Troubleshooting Problems with MSDTC" in BizTalk Server Help at [http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee72-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ee72-112">See Also</span></span>  
 [<span data-ttu-id="2ee72-113">Lista de comprobación: configuración de Windows Server</span><span class="sxs-lookup"><span data-stu-id="2ee72-113">Checklist: Configuring Windows Server</span></span>](../technical-guides/checklist-configuring-windows-server.md)