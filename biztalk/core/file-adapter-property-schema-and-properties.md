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
# <a name="file-adapter-property-schema-and-properties"></a>Propiedades y esquema de propiedades de adaptador de archivo
La tabla siguiente contiene las propiedades del esquema de propiedades del adaptador de archivo.  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties  
  
|Nombre|Tipo|Description|  
|----------|----------|-----------------|  
|**CopyMode**|xs:unsignedInt|Define el modo de copia que se utilizará al escribir un mensaje en un archivo. Los valores válidos son:<br /><br /> **Append (0).** El controlador de envío de archivo abre un archivo, si existe, y anexa un mensaje al final del archivo. Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.<br /><br /> **Crear nuevo (1).** Si el archivo no existe, el controlador de envío de archivo crea un archivo nuevo para escribir en él. Si el archivo ya existe, el controlador de envío de archivo notifica un error y sigue la lógica de reintento de adaptador común para los puertos de envío. Éste el modo de copia predeterminado para el controlador de envío de archivo.<br /><br /> **Sobrescribir (2).** El controlador de envío de archivo abre un archivo, si existe, y sobrescribe su contenido. Si el archivo no existe, el controlador de envío de archivo crea un nuevo archivo.|  
|**AllowCacheOnWrite**|xs:Boolean|Define si el adaptador de archivo utiliza el almacenamiento en caché del sistema de archivos al escribir un mensaje en un archivo.|  
|**ReceivedFileName**|xs:string|Define el nombre completo del archivo en el que el adaptador de archivo leerá el mensaje.|  
|**FileCreationTime**|xs:datetime|Define la hora en que se escribió el archivo en la carpeta supervisada por el adaptador de recepción de archivo.|  
|**Nombre de usuario**|xs:string|Define el nombre de usuario de la cuenta utilizada para especificar credenciales alternativas de acceso a recursos compartidos de red.|  
|**Contraseña**|xs:string|Define la contraseña de la cuenta utilizada para especificar credenciales alternativas de acceso a recursos compartidos de red.|  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador de archivo](../core/configure-the-file-adapter.md)