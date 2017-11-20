---
title: Los paquetes DTS de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 105d1b42848b73505d9a82df07693111708ce802
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-dts-packages"></a><span data-ttu-id="111ba-102">Paquetes DTS de BAM</span><span class="sxs-lookup"><span data-stu-id="111ba-102">BAM DTS Packages</span></span>
<span data-ttu-id="111ba-103">Un administrador puede actualizar parámetros para los siguientes paquetes DTS de BAM:</span><span class="sxs-lookup"><span data-stu-id="111ba-103">An administrator can update parameters for the following BAM DTS packages:</span></span>  
  
-   <span data-ttu-id="111ba-104">El **CubeUpdate** paquete de servicios de transformación de datos (DTS) siempre se encuentra en el mismo servidor que la base de datos de esquema de estrella.</span><span class="sxs-lookup"><span data-stu-id="111ba-104">The **CubeUpdate** Data Transformation Services (DTS) package is always located on the same server as the Star Schema database.</span></span>  
  
-   <span data-ttu-id="111ba-105">El **DataMaintenance** paquete DTS siempre se encuentra en el mismo servidor que la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="111ba-105">The **DataMaintenance** DTS package is always located on the same server as the Primary Import database.</span></span>  
  
 <span data-ttu-id="111ba-106">Los paquetes DTS utilizan los siguientes parámetros en el archivo BAMConfiguration.xml.</span><span class="sxs-lookup"><span data-stu-id="111ba-106">The DTS packages use the following parameters in the BAMConfiguration.xml file.</span></span>  
  
|<span data-ttu-id="111ba-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="111ba-107">Parameter</span></span>|<span data-ttu-id="111ba-108">Description</span><span class="sxs-lookup"><span data-stu-id="111ba-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="111ba-109">ConnectionTimeOut</span><span class="sxs-lookup"><span data-stu-id="111ba-109">ConnectionTimeOut</span></span>|<span data-ttu-id="111ba-110">El valor de tiempo de espera (en segundos) de la conexión DTS es un entero.</span><span class="sxs-lookup"><span data-stu-id="111ba-110">The DTS connection time out value (in seconds) is an integer.</span></span> <span data-ttu-id="111ba-111">Si omite el parámetro ConnectionTimeOut, el archivo de configuración utilizará 60 segundos (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="111ba-111">If you omit the ConnectionTimeOut parameter, the configuration file uses 60 seconds, the default value.</span></span>|  
|<span data-ttu-id="111ba-112">Cifrado</span><span class="sxs-lookup"><span data-stu-id="111ba-112">Encryption</span></span>|<span data-ttu-id="111ba-113">De forma predeterminada, los paquetes DTS no cifran los datos mientras los transforman (el valor Encryption es 0).</span><span class="sxs-lookup"><span data-stu-id="111ba-113">By default, the DTS packages do not encrypt data while they transform the data (Encryption value is 0).</span></span> <span data-ttu-id="111ba-114">Defina Encryption como 1 para cifrar los datos durante la transformación.</span><span class="sxs-lookup"><span data-stu-id="111ba-114">Set Encryption to 1 to encrypt the data during transformation.</span></span>|  
|<span data-ttu-id="111ba-115">OwnerPassword</span><span class="sxs-lookup"><span data-stu-id="111ba-115">OwnerPassword</span></span>|<span data-ttu-id="111ba-116">Es la contraseña del propietario del paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="111ba-116">The password for the DTS package owner.</span></span> <span data-ttu-id="111ba-117">Los propietarios de paquetes DTS pueden abrir y modificar paquetes DTS.</span><span class="sxs-lookup"><span data-stu-id="111ba-117">DTS package owners can open and modify DTS packages.</span></span> <span data-ttu-id="111ba-118">Para obtener información acerca de los propietarios de paquete DTS, consulte Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="111ba-118">For information about DTS package owners, see SQL Server Books Online.</span></span>|  
|<span data-ttu-id="111ba-119">UserPassword</span><span class="sxs-lookup"><span data-stu-id="111ba-119">UserPassword</span></span>|<span data-ttu-id="111ba-120">Es la contraseña del usuario DTS.</span><span class="sxs-lookup"><span data-stu-id="111ba-120">The password for the DTS user.</span></span> <span data-ttu-id="111ba-121">Los usuarios de paquetes DTS pueden ejecutar paquetes DTS.</span><span class="sxs-lookup"><span data-stu-id="111ba-121">DTS package users can run DTS packages.</span></span> <span data-ttu-id="111ba-122">Para obtener información acerca de los usuarios de paquetes DTS, consulte Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="111ba-122">For information about DTS package users, see SQL Server Books Online.</span></span>|  
  
 <span data-ttu-id="111ba-123">Los paquetes DTS utilizan las siguientes convenciones de nomenclatura en el archivo BAMConfiguration.xml.</span><span class="sxs-lookup"><span data-stu-id="111ba-123">The DTS packages use the following naming conventions in the BAMConfiguration.xml file:</span></span>  
  
-   <span data-ttu-id="111ba-124">**CubeUpdate** paquete DTS</span><span class="sxs-lookup"><span data-stu-id="111ba-124">**CubeUpdate** DTS package</span></span>  
  
     <span data-ttu-id="111ba-125">**bam_AN_\<** </span><span class="sxs-lookup"><span data-stu-id="111ba-125">**bam_AN_\<** </span></span>  
     <span data-ttu-id="111ba-126">***CubeName* >**, donde CubeName es el nombre del cubo.</span><span class="sxs-lookup"><span data-stu-id="111ba-126">***CubeName* >**, where CubeName is the name of the cube.</span></span> <span data-ttu-id="111ba-127">El libro de trabajo de BAM genera el nombre de cubo a partir del nombre de vista.</span><span class="sxs-lookup"><span data-stu-id="111ba-127">The BAM workbook generates the cube name from the view name.</span></span> <span data-ttu-id="111ba-128">Si modifica el nombre del cubo en el documento XML de configuración de BAM, el nuevo nombre del cubo se usa en el nombre del paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="111ba-128">If you modify the cube name in the BAM configuration XML document, the new cube name is used in the DTS package name.</span></span>  
  
-   <span data-ttu-id="111ba-129">**DataMaintenance** paquete DTS</span><span class="sxs-lookup"><span data-stu-id="111ba-129">**DataMaintenance** DTS package</span></span>  
  
     <span data-ttu-id="111ba-130">**bam_DM_\<** </span><span class="sxs-lookup"><span data-stu-id="111ba-130">**bam_DM_\<** </span></span>  
     <span data-ttu-id="111ba-131">***ActivityName* >**, donde ActivityName es el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="111ba-131">***ActivityName* >**, where ActivityName is the name of the activity.</span></span>  
  
 <span data-ttu-id="111ba-132">El paquete DTS CubeUpdate se utiliza para añadir la agregación programada.</span><span class="sxs-lookup"><span data-stu-id="111ba-132">You run the CubeUpdate DTS package to aggregate the scheduled aggregation.</span></span> <span data-ttu-id="111ba-133">En la sección siguiente, podrá especificar el período de tiempo para agregación de datos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="111ba-133">In the next section, you can specify the time window for real-time data aggregation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111ba-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="111ba-134">See Also</span></span>  
 <span data-ttu-id="111ba-135">[Esquema de configuración de BAM](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="111ba-135">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="111ba-136">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="111ba-136">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="111ba-137">Administración de BAM</span><span class="sxs-lookup"><span data-stu-id="111ba-137">Managing BAM</span></span>](../core/managing-bam.md)