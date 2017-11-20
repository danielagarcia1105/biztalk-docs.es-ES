---
title: "Archivos de configuración de servicios de Script de línea de comandos de BAM para la notificación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aa4a460-58f9-439d-af28-0a9cb2288236
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6950326994e99dcbc2ecff49a36f7441f3c219d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bam-command-line-script-for-notification-services-configuration-files"></a><span data-ttu-id="b0e61-102">Secuencia de comandos de línea de comandos de BAM para archivos de configuración de servicios de notificación</span><span class="sxs-lookup"><span data-stu-id="b0e61-102">BAM Command-Line Script for Notification Services Configuration Files</span></span>
<span data-ttu-id="b0e61-103">Los administradores utilizan la secuencia de comandos ProcessBamNSFiles.vbs para personalizar el comportamiento de los servicios de notificación de SQL Server para alertas BAM.</span><span class="sxs-lookup"><span data-stu-id="b0e61-103">Administrators use the ProcessBamNSFiles.vbs script to customize the behavior of SQL Server Notification Services for BAM alerts.</span></span> <span data-ttu-id="b0e61-104">Puede utilizar la secuencia de comandos para obtener el archivo de definición de la aplicación (ADF) de servicios de notificación y el archivo de configuración de servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="b0e61-104">You can use the script to obtain the Notification Services application definition file (ADF) and Notification Services configuration file.</span></span> <span data-ttu-id="b0e61-105">Estos archivos se pueden modificar y, a continuación, se puede utilizar la secuencia de comandos para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b0e61-105">These files can be modified and then the script can be used to apply the changes.</span></span>  
  
 <span data-ttu-id="b0e61-106">La secuencia de comandos se ejecuta desde un símbolo del sistema de servicios de notificación y no desde un símbolo de sistema común.</span><span class="sxs-lookup"><span data-stu-id="b0e61-106">You run the script from a Notification Services command prompt and not from a typical command prompt.</span></span> <span data-ttu-id="b0e61-107">Si se ejecuta la secuencia de comandos desde un símbolo de sistema común, la secuencia de comandos se ejecutará incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="b0e61-107">Running the script from a typical command prompt will cause the script to execute incorrectly.</span></span> <span data-ttu-id="b0e61-108">Cuando se ejecuta la secuencia de comandos, todos los parámetros son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="b0e61-108">When running the script all parameters are mandatory.</span></span>  
  
## <a name="get-command"></a><span data-ttu-id="b0e61-109">Get (comando)</span><span class="sxs-lookup"><span data-stu-id="b0e61-109">Get command</span></span>  
 <span data-ttu-id="b0e61-110">**Uso**</span><span class="sxs-lookup"><span data-stu-id="b0e61-110">**Usage**</span></span>  
  
 <span data-ttu-id="b0e61-111">**cscript ProcessBamNSFiles-Get \<ruta de acceso de archivo de configuración > \<ruta del archivo ADF > \<servidor de importación principal > \<base de datos de importación principal de >**</span><span class="sxs-lookup"><span data-stu-id="b0e61-111">**cscript ProcessBamNSFiles -Get \<configuration file path> \<ADF file path>  \<primary import server> \<primary import database>**</span></span>  
  
|<span data-ttu-id="b0e61-112">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b0e61-112">Parameter</span></span>|<span data-ttu-id="b0e61-113">Description</span><span class="sxs-lookup"><span data-stu-id="b0e61-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0e61-114">ruta del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b0e61-114">configuration file path</span></span>|<span data-ttu-id="b0e61-115">Especifica el nombre y la ubicación en la que se va a almacenar el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b0e61-115">Specifies the name and location in which to store the configuration file.</span></span>|  
|<span data-ttu-id="b0e61-116">ruta del archivo ADF</span><span class="sxs-lookup"><span data-stu-id="b0e61-116">ADF file path</span></span>|<span data-ttu-id="b0e61-117">Especifica el nombre y la ubicación en la que se va a almacenar el archivo ADF.</span><span class="sxs-lookup"><span data-stu-id="b0e61-117">Specifies the name and location in which to store the ADF file.</span></span>|  
|<span data-ttu-id="b0e61-118">servidor de importación principal</span><span class="sxs-lookup"><span data-stu-id="b0e61-118">primary import server</span></span>|<span data-ttu-id="b0e61-119">Nombre del equipo en el que se almacena la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b0e61-119">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="b0e61-120">base de datos de importación principal</span><span class="sxs-lookup"><span data-stu-id="b0e61-120">primary import database</span></span>|<span data-ttu-id="b0e61-121">Nombre de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b0e61-121">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="b0e61-122">Recupera los archivos de definición de la aplicación y de configuración de servicios de notificación de la base de datos de importación principal de BAM y los guarda en las rutas especificadas.</span><span class="sxs-lookup"><span data-stu-id="b0e61-122">Retrieves the Notification Services configuration and application definition files from the BAM Primary Import database and saves them to specified paths.</span></span>  
  
## <a name="update-command"></a><span data-ttu-id="b0e61-123">Update (comando)</span><span class="sxs-lookup"><span data-stu-id="b0e61-123">Update command</span></span>  
 <span data-ttu-id="b0e61-124">**Uso**</span><span class="sxs-lookup"><span data-stu-id="b0e61-124">**Usage**</span></span>  
  
 <span data-ttu-id="b0e61-125">**cscript ProcessBamNSFiles-Update \<configfilepath > \<adffilepath > \<primaryimport server > \<base de datos de importación principal de >**</span><span class="sxs-lookup"><span data-stu-id="b0e61-125">**cscript ProcessBamNSFiles -Update \<configfilepath> \<adffilepath>  \<primaryimport server> \<primary import db>**</span></span>  
  
|<span data-ttu-id="b0e61-126">Parámetro</span><span class="sxs-lookup"><span data-stu-id="b0e61-126">Parameter</span></span>|<span data-ttu-id="b0e61-127">Description</span><span class="sxs-lookup"><span data-stu-id="b0e61-127">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0e61-128">ruta del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b0e61-128">configuration file path</span></span>|<span data-ttu-id="b0e61-129">Especifica el nombre y la ubicación desde la que se va a actualizar la información de configuración de servicios de notificación.</span><span class="sxs-lookup"><span data-stu-id="b0e61-129">Specifies the name and location from which to update the Notification Services configuration information.</span></span>|  
|<span data-ttu-id="b0e61-130">ruta del archivo ADF</span><span class="sxs-lookup"><span data-stu-id="b0e61-130">ADF file path</span></span>|<span data-ttu-id="b0e61-131">Especifica el nombre y la ubicación desde la que se va a actualizar la información de ADF.</span><span class="sxs-lookup"><span data-stu-id="b0e61-131">Specifies the name and location from which to update the ADF information.</span></span>|  
|<span data-ttu-id="b0e61-132">servidor de importación principal</span><span class="sxs-lookup"><span data-stu-id="b0e61-132">primary import server</span></span>|<span data-ttu-id="b0e61-133">Nombre del equipo en el que se almacena la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b0e61-133">Name of the computer on which the BAM Primary Import database is stored.</span></span>|  
|<span data-ttu-id="b0e61-134">base de datos de importación principal</span><span class="sxs-lookup"><span data-stu-id="b0e61-134">primary import database</span></span>|<span data-ttu-id="b0e61-135">Nombre de la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b0e61-135">Name of the BAM Primary Import database.</span></span>|  
  
 <span data-ttu-id="b0e61-136">Llama a servicios de notificación y actualiza la configuración con la información de los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="b0e61-136">Calls Notification Services and updates the settings with the information in the specified files.</span></span> <span data-ttu-id="b0e61-137">Los archivos ADF y los de configuración se almacenan en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="b0e61-137">The configuration and ADF files are stored in the BAM Primary Import database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e61-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0e61-138">See Also</span></span>  
 [<span data-ttu-id="b0e61-139">Herramientas de línea de comandos de BAM</span><span class="sxs-lookup"><span data-stu-id="b0e61-139">BAM Command-Line Tools</span></span>](../core/bam-command-line-tools.md)