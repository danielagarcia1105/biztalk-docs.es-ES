---
title: "Implementación Limitations2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deployment, limitations
- passwords, adapter limitations
ms.assetid: 9db2ca70-5db2-4b14-a898-13049737c188
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05fa9704823bd7e9df9f0bc7d4516719a8a490e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-limitations"></a>Limitaciones de implementación
La contraseña del adaptador de transporte se almacena como asteriscos (\*\*\*\*\*\*) en el archivo de enlace que se ha exportado por el Asistente para implementar BizTalk y se pasa a la administración componente en el mismo formato. Edite el archivo de enlace antes de la importación. Para ello, reemplace los asteriscos por valores alfanuméricos aleatorios (es decir, una contraseña que no sea la correcta). A continuación, escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.  
  
 Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.  
  
> [!NOTE]
>  Al importar un archivo .msi en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, es posible que aparezca un mensaje de error de importación. Está disponible de Microsoft junto con una descripción completa del error en una revisión compatible [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).  
  
## <a name="password-limitation-workaround"></a>Solución para la limitación de contraseña  
 Use una de las siguientes soluciones como alternativa para la limitación de contraseña.  
  
#### <a name="to-work-around-the-password-limitation"></a>Para solucionar la limitación de contraseña  
  
1.  Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.  
  
    > [!CAUTION]
    >  Por motivos de seguridad, esta práctica no es recomendable.  
  
2.  Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.  
  
    > [!NOTE]
    >  Esta solución solo puede usarse si Microsoft Visual Studio se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.  
  
 **O bien**  
  
#### <a name="to-work-around-the-password-limitation"></a>Para solucionar la limitación de contraseña  
  
1.  Use el inicio de sesión único empresarial en lugar de contraseñas.  
  
     El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.  
  
2.  Compruebe el sistema lógico y los servicios de transmisión y recepción.  
  
## <a name="see-also"></a>Vea también  
 [Cómo establecer las propiedades de transporte de OneWorld JD Edwards](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)   
 [Implementación de puertos y ensamblados](../core/deploying-ports-and-assemblies4.md)