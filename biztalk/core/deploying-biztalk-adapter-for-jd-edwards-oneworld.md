---
title: Importar el adaptador de BizTalk para JD Edwards OneWorld | Documentos de Microsoft
description: Importe el archivo de enlace de la aplicación y revisar las limitaciones del adaptador de JD Edwards OneWorld en BizTalk
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f308d2fe-39dd-4008-94ed-292c4c26fe06
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a452d61b3bdb5f5d0fee9e0916811645938d70
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25969986"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a>Importar la aplicación JD Edwards EnterpriseOne
  
## <a name="overview"></a>Información general
Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino. BizTalk Server exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.  
  
 Puede usar BizTalk Server para realizar las tareas siguientes:  
  
-   Implementar o quitar los ensamblados de BizTalk Server en una base de datos de configuración de BizTalk  
  
-   Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)  
  
-   Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace  

Usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).  
  
> [!NOTE]
>  El adaptador de Microsoft BizTalk para JD Edwards OneWorld solo necesita que tenga Visual Studio en un equipo de origen (desarrollo). Visual Studio no es necesario en el equipo de producción.  

## <a name="confirm-your-setup"></a>Confirme la configuración
Antes de utilizar el servidor BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:  
  
-   CLASSPATH apunta a una ubicación específica para los archivos específicos de JD Edwards. Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.  
  
-   Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.  
  
-   Las contraseñas del sistema de JD Edwards, si hay en la configuración se guardan como ***** en el archivo de enlaces. Vea **limitaciones** en este tema.

  
> [!NOTE]
>  La implementación sobrescribe la configuración de ubicación de recepción. Al implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.  
  
  
## <a name="clean-the-target-computer"></a>Limpiar el equipo de destino
Implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.  
  
Antes de importar, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.  
  
Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
-   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
Por ejemplo, en un símbolo del sistema, ejecute:  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="limitations"></a>Limitaciones
La contraseña del adaptador de transporte se almacena como asteriscos (\*\*\*\*\*\*) en el archivo de enlace que se ha exportado por el Asistente para implementar BizTalk y se pasa a la administración componente en el mismo formato. Edite el archivo de enlace antes de la importación. Para ello, reemplace los asteriscos por valores alfanuméricos aleatorios (es decir, una contraseña que no sea la correcta). A continuación, escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.  
  
 Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.  
  
> [!NOTE]
>  Al importar un archivo .msi en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, es posible que aparezca un mensaje de error de importación. Está disponible de Microsoft junto con una descripción completa del error en una revisión compatible [ http://support.microsoft.com/kb/923733/en-us ](http://support.microsoft.com/kb/923733/en-us).  
  
### <a name="work-around-the-password-limitation"></a>Evitar la limitación de contraseña  

**opción 1**  

- Antes de importar, actualice el archivo de enlace reemplazando los asteriscos por texto sin formato.  
  
    > [!CAUTION]
    >  Por motivos de seguridad, esta práctica no es recomendable.  
  
- Antes de importar, actualice el archivo de enlace reemplazando los asteriscos por un valor aleatorio (es decir, no la contraseña correcta). Después de importar, escriba la contraseña correcta mediante la **propiedades de transporte**.  
  
    > [!NOTE]
    >  Esta solución solo puede usarse si Microsoft Visual Studio se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.  
  
**Opción 2**  
  
1.  Use el inicio de sesión único empresarial en lugar de contraseñas. El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.  
  
2.  Compruebe el sistema lógico y los servicios de transmisión y recepción.  

## <a name="next-steps"></a>Pasos siguientes
[Usar el control de excepciones de BizTalk Server en la orquestación](../core/using-biztalk-server-exception-handling1.md)