---
title: Los paquetes DTS de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DTS packages, BAM
- BAM, DTS packages
ms.assetid: bba70d81-6ddf-4f1f-a1f7-d5a5bf453bae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e49741a0fce6fd69e4e2ba5d8bb8dbd1956a0e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015853"
---
# <a name="bam-dts-packages"></a><span data-ttu-id="a57d0-102">Paquetes DTS de BAM</span><span class="sxs-lookup"><span data-stu-id="a57d0-102">BAM DTS Packages</span></span>
<span data-ttu-id="a57d0-103">Un administrador puede actualizar parámetros para los siguientes paquetes DTS de BAM:</span><span class="sxs-lookup"><span data-stu-id="a57d0-103">An administrator can update parameters for the following BAM DTS packages:</span></span>  
  
- <span data-ttu-id="a57d0-104">El **CubeUpdate** siempre se encuentra el paquete de servicios de transformación de datos (DTS) en el mismo servidor que la base de datos de esquema de estrella.</span><span class="sxs-lookup"><span data-stu-id="a57d0-104">The **CubeUpdate** Data Transformation Services (DTS) package is always located on the same server as the Star Schema database.</span></span>  
  
- <span data-ttu-id="a57d0-105">El **DataMaintenance** siempre se encuentra el paquete DTS en el mismo servidor que la base de datos de importación principal.</span><span class="sxs-lookup"><span data-stu-id="a57d0-105">The **DataMaintenance** DTS package is always located on the same server as the Primary Import database.</span></span>  
  
  <span data-ttu-id="a57d0-106">Los paquetes DTS utilizan los siguientes parámetros en el archivo BAMConfiguration.xml.</span><span class="sxs-lookup"><span data-stu-id="a57d0-106">The DTS packages use the following parameters in the BAMConfiguration.xml file.</span></span>  
  
|<span data-ttu-id="a57d0-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a57d0-107">Parameter</span></span>|<span data-ttu-id="a57d0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a57d0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a57d0-109">ConnectionTimeOut</span><span class="sxs-lookup"><span data-stu-id="a57d0-109">ConnectionTimeOut</span></span>|<span data-ttu-id="a57d0-110">El valor de tiempo de espera (en segundos) de la conexión DTS es un entero.</span><span class="sxs-lookup"><span data-stu-id="a57d0-110">The DTS connection time out value (in seconds) is an integer.</span></span> <span data-ttu-id="a57d0-111">Si omite el parámetro ConnectionTimeOut, el archivo de configuración utilizará 60 segundos (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="a57d0-111">If you omit the ConnectionTimeOut parameter, the configuration file uses 60 seconds, the default value.</span></span>|  
|<span data-ttu-id="a57d0-112">Cifrado</span><span class="sxs-lookup"><span data-stu-id="a57d0-112">Encryption</span></span>|<span data-ttu-id="a57d0-113">De forma predeterminada, los paquetes DTS no cifran los datos mientras los transforman (el valor Encryption es 0).</span><span class="sxs-lookup"><span data-stu-id="a57d0-113">By default, the DTS packages do not encrypt data while they transform the data (Encryption value is 0).</span></span> <span data-ttu-id="a57d0-114">Defina Encryption como 1 para cifrar los datos durante la transformación.</span><span class="sxs-lookup"><span data-stu-id="a57d0-114">Set Encryption to 1 to encrypt the data during transformation.</span></span>|  
|<span data-ttu-id="a57d0-115">OwnerPassword</span><span class="sxs-lookup"><span data-stu-id="a57d0-115">OwnerPassword</span></span>|<span data-ttu-id="a57d0-116">Es la contraseña del propietario del paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="a57d0-116">The password for the DTS package owner.</span></span> <span data-ttu-id="a57d0-117">Los propietarios de paquetes DTS pueden abrir y modificar paquetes DTS.</span><span class="sxs-lookup"><span data-stu-id="a57d0-117">DTS package owners can open and modify DTS packages.</span></span> <span data-ttu-id="a57d0-118">Para obtener información acerca de los propietarios de paquete DTS, consulte Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a57d0-118">For information about DTS package owners, see SQL Server Books Online.</span></span>|  
|<span data-ttu-id="a57d0-119">UserPassword</span><span class="sxs-lookup"><span data-stu-id="a57d0-119">UserPassword</span></span>|<span data-ttu-id="a57d0-120">Es la contraseña del usuario DTS.</span><span class="sxs-lookup"><span data-stu-id="a57d0-120">The password for the DTS user.</span></span> <span data-ttu-id="a57d0-121">Los usuarios de paquetes DTS pueden ejecutar paquetes DTS.</span><span class="sxs-lookup"><span data-stu-id="a57d0-121">DTS package users can run DTS packages.</span></span> <span data-ttu-id="a57d0-122">Para obtener información acerca de los usuarios de paquetes DTS, consulte Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a57d0-122">For information about DTS package users, see SQL Server Books Online.</span></span>|  
  
 <span data-ttu-id="a57d0-123">Los paquetes DTS utilizan las siguientes convenciones de nomenclatura en el archivo BAMConfiguration.xml.</span><span class="sxs-lookup"><span data-stu-id="a57d0-123">The DTS packages use the following naming conventions in the BAMConfiguration.xml file:</span></span>  
  
- <span data-ttu-id="a57d0-124">**CubeUpdate** paquete DTS</span><span class="sxs-lookup"><span data-stu-id="a57d0-124">**CubeUpdate** DTS package</span></span>  
  
   <span data-ttu-id="a57d0-125">**bam_AN_\<**  ***CubeName* \>**, donde CubeName es el nombre del cubo.</span><span class="sxs-lookup"><span data-stu-id="a57d0-125">**bam_AN_\<** ***CubeName* \>**, where CubeName is the name of the cube.</span></span> <span data-ttu-id="a57d0-126">El libro de trabajo de BAM genera el nombre de cubo a partir del nombre de vista.</span><span class="sxs-lookup"><span data-stu-id="a57d0-126">The BAM workbook generates the cube name from the view name.</span></span> <span data-ttu-id="a57d0-127">Si modifica el nombre del cubo en el documento XML de configuración de BAM, el nuevo nombre del cubo se usa en el nombre del paquete DTS.</span><span class="sxs-lookup"><span data-stu-id="a57d0-127">If you modify the cube name in the BAM configuration XML document, the new cube name is used in the DTS package name.</span></span>  
  
- <span data-ttu-id="a57d0-128">**DataMaintenance** paquete DTS</span><span class="sxs-lookup"><span data-stu-id="a57d0-128">**DataMaintenance** DTS package</span></span>  
  
   <span data-ttu-id="a57d0-129">**bam_DM_\<**  ***ActivityName* \>**, donde ActivityName es el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a57d0-129">**bam_DM_\<** ***ActivityName* \>**, where ActivityName is the name of the activity.</span></span>  
  
  <span data-ttu-id="a57d0-130">El paquete DTS CubeUpdate se utiliza para añadir la agregación programada.</span><span class="sxs-lookup"><span data-stu-id="a57d0-130">You run the CubeUpdate DTS package to aggregate the scheduled aggregation.</span></span> <span data-ttu-id="a57d0-131">En la sección siguiente, podrá especificar el período de tiempo para agregación de datos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="a57d0-131">In the next section, you can specify the time window for real-time data aggregation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57d0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a57d0-132">See Also</span></span>  
 <span data-ttu-id="a57d0-133">[Esquema de configuración de BAM](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="a57d0-133">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 <span data-ttu-id="a57d0-134">[Recomendaciones de seguridad BAM](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="a57d0-134">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="a57d0-135">Administración de BAM</span><span class="sxs-lookup"><span data-stu-id="a57d0-135">Managing BAM</span></span>](../core/managing-bam.md)