---
title: Importar aplicaciones de JD Edwards EnterpriseOne | Documentos de Microsoft
description: Confirmar la instalación, importe el archivo de enlace de la aplicación y revisar las limitaciones del adaptador de JD Edwards EnterpriseOne en BizTalk
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55374c87192c993e26cc11cb496d89074d527868
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25969676"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>Importar la aplicación JD Edwards EnterpriseOne
  
## <a name="overview"></a>Información general
Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede duplicar puertos y ensamblados en un equipo de destino. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.  
  
 Puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las tareas siguientes:  
  
-   Implementar o quitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados en una base de datos de configuración de BizTalk  
  
-   Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)  
  
-   Importar o exportar información de vínculos de ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde y a archivos de vínculos  
  
Usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).  
  
> [!NOTE]
>  El adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne solo necesita que tenga Visual Studio en un equipo de origen (desarrollo). Visual Studio no es necesario en el equipo de producción.  

## <a name="confirm-your-setup"></a>Confirme la configuración
Antes de usar BizTalk Server para importar un archivo de enlace, debe comprobar lo siguiente:  
  
-   CLASSPATH apunta a una ubicación concreta para los archivos específicos de JD Edwards EnterpriseOne. Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.  
  
-   Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.  
  
-   Las contraseñas del sistema JD Edwards EnterpriseOne, si están presentes en la configuración, se guardan como ***** en el archivo de enlace. Para obtener más información, consulte **limitaciones** en este tema.

## <a name="clean-the-target-computer"></a>Limpiar el equipo de destino
Al volver a implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se vuelven a importar.  
  
Antes de importar, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación. Si Visual Studio no está instalado en el equipo de destino, puede quitar los puertos ejecutando estos scripts:  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  

Por ejemplo, desde un símbolo del sistema, ejecute:  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a>Limitaciones
La contraseña del adaptador de transporte se almacena como estrellas (*) en el archivo de enlace exportado por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y pasa al componente de administración en el mismo formato. Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).  
  
 Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.  
  
 También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.  
  
### <a name="work-around-the-password-limitation"></a>Evitar la limitación de contraseña  
  
1.  Use el inicio de sesión único empresarial en lugar de contraseñas. El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.  
  
2.  Compruebe el sistema lógico y los servicios de transmisión y recepción.  


## <a name="next-steps"></a>Pasos siguientes
[Usar el control de excepciones de BizTalk Server en la orquestación](../core/using-biztalk-server-exception-handling3.md)