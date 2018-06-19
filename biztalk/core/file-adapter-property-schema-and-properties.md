---
title: Propiedades y esquema de propiedades de adaptador de archivo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], properties
- schemas, File adapters
- File adapters, schemas
- Password property [File adapters]
- ReceivedFileName property [File adapters]
- configuring [File adapters], schemas
- CopyMode property [File adapters]
- AllowCacheOnWrite property [File adapters]
- FileCreationTime property [File adapters]
- UserName property, File adapters
- File adapters, properties
- UserName property
ms.assetid: c5ae5339-67bf-4fde-a721-5b1aa3b9caca
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e1c6860b002b41555337a0bf7e8cb931f2c2bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245996"
---
# <a name="file-adapter-property-schema-and-properties"></a><span data-ttu-id="63064-102">Propiedades y esquema de propiedades de adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="63064-102">File adapter property schema and properties</span></span>
<span data-ttu-id="63064-103">La tabla siguiente contiene las propiedades del esquema de propiedades del adaptador de archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-103">The following table contains the properties in the File adapter property schema.</span></span>  
  
 <span data-ttu-id="63064-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span><span class="sxs-lookup"><span data-stu-id="63064-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span></span>  
  
|<span data-ttu-id="63064-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="63064-105">Name</span></span>|<span data-ttu-id="63064-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="63064-106">Type</span></span>|<span data-ttu-id="63064-107">Description</span><span class="sxs-lookup"><span data-stu-id="63064-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="63064-108">**CopyMode**</span><span class="sxs-lookup"><span data-stu-id="63064-108">**CopyMode**</span></span>|<span data-ttu-id="63064-109">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="63064-109">xs:unsignedInt</span></span>|<span data-ttu-id="63064-110">Define el modo de copia que se utilizará al escribir un mensaje en un archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-110">Defines the copy mode to use when writing a message to a file.</span></span> <span data-ttu-id="63064-111">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="63064-111">Valid values are:</span></span><br /><br /> <span data-ttu-id="63064-112">**Append (0).**</span><span class="sxs-lookup"><span data-stu-id="63064-112">**Append (0).**</span></span> <span data-ttu-id="63064-113">El controlador de envío de archivo abre un archivo, si existe, y anexa un mensaje al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-113">The File send handler opens a file if it exists and appends a message to the end of the file.</span></span> <span data-ttu-id="63064-114">Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-114">If the file does not exist, the File send handler creates a new file.</span></span><br /><br /> <span data-ttu-id="63064-115">**Crear nuevo (1).**</span><span class="sxs-lookup"><span data-stu-id="63064-115">**Create new (1).**</span></span> <span data-ttu-id="63064-116">Si el archivo no existe, el controlador de envío de archivo crea un archivo nuevo para escribir en él.</span><span class="sxs-lookup"><span data-stu-id="63064-116">If a file does not exist, the File send handler creates a new file and writes to it.</span></span> <span data-ttu-id="63064-117">Si el archivo ya existe, el controlador de envío de archivo notifica un error y sigue la lógica de reintento de adaptador común para los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="63064-117">If the file already exists, the File send handler reports an error and then follows common adapter retry logic for send ports.</span></span> <span data-ttu-id="63064-118">Éste el modo de copia predeterminado para el controlador de envío de archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-118">This is a default copy mode for the File send handler.</span></span><br /><br /> <span data-ttu-id="63064-119">**Sobrescribir (2).**</span><span class="sxs-lookup"><span data-stu-id="63064-119">**Overwrite (2).**</span></span> <span data-ttu-id="63064-120">El controlador de envío de archivo abre un archivo, si existe, y sobrescribe su contenido.</span><span class="sxs-lookup"><span data-stu-id="63064-120">The File send handler opens a file if it exists and overwrites its content.</span></span> <span data-ttu-id="63064-121">Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-121">If the file does not exist, the File send handler creates a new file.</span></span>|  
|<span data-ttu-id="63064-122">**AllowCacheOnWrite**</span><span class="sxs-lookup"><span data-stu-id="63064-122">**AllowCacheOnWrite**</span></span>|<span data-ttu-id="63064-123">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="63064-123">xs:Boolean</span></span>|<span data-ttu-id="63064-124">Define si el adaptador de archivo utiliza el almacenamiento en caché del sistema de archivos al escribir un mensaje en un archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-124">Defines whether the File adapter uses file system caching when writing messages to a file.</span></span>|  
|<span data-ttu-id="63064-125">**ReceivedFileName**</span><span class="sxs-lookup"><span data-stu-id="63064-125">**ReceivedFileName**</span></span>|<span data-ttu-id="63064-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="63064-126">xs:string</span></span>|<span data-ttu-id="63064-127">Define el nombre completo del archivo en el que el adaptador de archivo leerá el mensaje.</span><span class="sxs-lookup"><span data-stu-id="63064-127">Defines the full name of the file from which the File adapter reads the message.</span></span>|  
|<span data-ttu-id="63064-128">**FileCreationTime**</span><span class="sxs-lookup"><span data-stu-id="63064-128">**FileCreationTime**</span></span>|<span data-ttu-id="63064-129">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="63064-129">xs:datetime</span></span>|<span data-ttu-id="63064-130">Define la hora en que se escribió el archivo en la carpeta supervisada por el adaptador de recepción de archivo.</span><span class="sxs-lookup"><span data-stu-id="63064-130">Defines the time that the file was written to the folder that is monitored by the File receive adapter.</span></span>|  
|<span data-ttu-id="63064-131">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="63064-131">**Username**</span></span>|<span data-ttu-id="63064-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="63064-132">xs:string</span></span>|<span data-ttu-id="63064-133">Define el nombre de usuario de la cuenta utilizada para especificar credenciales alternativas de acceso a recursos compartidos de red.</span><span class="sxs-lookup"><span data-stu-id="63064-133">Defines the user name for the account used when specifying alternative credentials to access a network share.</span></span>|  
|<span data-ttu-id="63064-134">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="63064-134">**Password**</span></span>|<span data-ttu-id="63064-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="63064-135">xs:string</span></span>|<span data-ttu-id="63064-136">Define la contraseña de la cuenta utilizada para especificar credenciales alternativas de acceso a recursos compartidos de red.</span><span class="sxs-lookup"><span data-stu-id="63064-136">Defines the password for the account used when specifying alternative credentials to access a network share.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63064-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="63064-137">See Also</span></span>  
 [<span data-ttu-id="63064-138">Configurar el adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="63064-138">Configuring the File Adapter</span></span>](../core/configure-the-file-adapter.md)