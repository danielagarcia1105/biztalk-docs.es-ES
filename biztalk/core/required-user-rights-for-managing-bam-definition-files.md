---
title: "Derechos de usuario necesarios para administrar archivos de definición de BAM | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb4fb73f-b783-4a04-9bd6-a135b3dd2655
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5e39c86eec0cf198a5b879cbc98d29321de71dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="required-user-rights-for-managing-bam-definition-files"></a>Derechos de usuario necesarios para administrar archivos de definición de BAM
Los usuarios con cualquier función podrán crear, administrar y ver los archivos de definición de BAM. La administración de archivos de definición de BAM incluye su implementación y eliminación, así como la administración de las actividades, vistas, alertas y artefactos asociados al archivo de definición.  
  
 Los administradores deberán mantener una correcta protección de los activos, por ejemplo, creando carpetas compartidas con los permisos de acceso apropiados. Al utilizar el complemento de BAM para Excel, se recomienda a los usuarios definir el nivel de seguridad de las macros como “alto”.  
  
 No se necesita ningún derecho de usuario para modificar los archivos de definición de BAM (dependiendo de los permisos establecidos en la ubicación de almacenamiento de los archivos de definición en cuestión). Los cambios realizados en los archivos de definición no se aplican automáticamente a la infraestructura de BAM. Para aplicar los cambios, deberá usar la utilidad de administración de BAM.  
  
 Para usar la utilidad de administración de BAM, deberá ser administrador en el equipo en que se esté aplicando la definición de BAM, o miembro del grupo de administradores de BizTalk Server.  
  
> [!NOTE]
>  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Administración de la infraestructura dinámica de BAM](../core/managing-the-bam-dynamic-infrastructure.md)   
 [¿Qué es una definición de BAM?](../core/what-is-a-bam-definition.md)   
 [Cómo implementar definiciones de BAM](../core/how-to-deploy-bam-definitions.md)