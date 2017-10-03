---
title: "Implementación Limitations1 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: deployment, limitations
ms.assetid: a984ccce-37b2-4738-b652-7232a18e0510
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e65fb1c1a1211865b07c3abb987f0a1d31fbfd69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>Limitaciones de implementación
La contraseña del adaptador de transporte se almacena como estrellas (\*\*\*\*\*\*) en el archivo de enlace que se ha exportado por BizTalk Server y pasa al componente de administración en el mismo formato. Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.  
  
 Se trata de una limitación conocida. Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación correctamente.  
  
> [!NOTE]
>  Al importar un archivo .msi en la aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, puede que aparezca un mensaje de error de la importación. Está disponible de Microsoft junto con una descripción completa del error en una revisión compatible [http://go.microsoft.com/fwlink/?LinkID=196087](http://go.microsoft.com/fwlink/?LinkID=196087).  
  
## <a name="password-limitation-workaround"></a>Solución para la limitación de contraseña  
 Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.  
  
> [!CAUTION]
>  Por motivos de seguridad, esta práctica no es recomendable.  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.  
  
> [!NOTE]
>  Esta solución solo se puede usar si Visual Studio está instalado en el equipo de destino, o si desarrolla una herramienta personalizada.  
  
-   Compruebe el sistema lógico y los servicios de transmisión y recepción.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de puertos y ensamblados](../core/deploying-ports-and-assemblies2.md)