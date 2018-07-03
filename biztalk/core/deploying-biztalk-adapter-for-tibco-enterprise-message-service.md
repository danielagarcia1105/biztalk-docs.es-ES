---
title: Importar enlaces para TIBCO EMS | Microsoft Docs
description: Implementar el adaptador de BizTalk para aplicaciones de TIBCO Enterprise Message Service mediante la característica Importar enlaces en BizTalk Server
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69dae448-4ec6-4a56-a628-bb447bc21b62
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e90d083833e7961770c6ecd535e9ed3e5143be30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981365"
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a>Implementar ensamblados y puertos de TIBCO EMS

## <a name="overview"></a>Información general
Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede duplicar puertos y ensamblados en un equipo de destino. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración de la ubicación de recepción/puertos de envío de exportaciones en un archivo XML.  
  
 Puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las tareas siguientes:  
  
- Implementar o quitar los ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una base de datos de configuración de BizTalk  
  
- Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)  
  
- Importar información de enlace de ensamblado de BizTalk a archivos de enlace o exportarla a ellos.  
  
  Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).  
  
> [!NOTE]
>  Microsoft BizTalk Adapter para TIBCO Enterprise Message Service solo necesita que disponga de Visual Studio en un equipo de origen (desarrollo). Visual Studio no es necesario en el equipo de producción.  

## <a name="confirm-your-setup"></a>Confirme la configuración
Antes de usar BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:  
  
-   Deben existir las carpetas para las respuestas y ser idénticas en el equipo nuevo, o bien debe editar el archivo.  
  
-   Las contraseñas del sistema TIBCO Enterprise Message Service, si están presentes en la configuración, se guardan como ***** en el archivo de enlace. Consulte **limitaciones** en este tema.


## <a name="clean-the-target-computer"></a>Limpiar el equipo de destino
Implementación sobrescribe la configuración de la ubicación de recepción. Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.  

Antes de importar, quite los puertos de envío y enlazadas a la orquestación de las ubicaciones de recepción.  
  
Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs`  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs`
  

Por ejemplo, en un símbolo del sistema, ejecute:  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a>Limitaciones
La contraseña del adaptador de transporte se almacena como estrellas (\*\*\*\*\*\*) en el archivo de enlace exportado por BizTalk Server, y pasa al componente de administración en la misma formato. Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.  
  
 Se trata de una limitación conocida. Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción. De este modo, se evita que la información de contraseña aparezca en texto no cifrado. La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte. También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo. En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación correctamente.  
  
 
### <a name="password-limitation-workaround"></a>Solución para la limitación de contraseña  
 Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.  
  
    > [!CAUTION]
    >  Por motivos de seguridad, esta práctica no es recomendable.  
  
-   Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta). Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.  
  
    > [!NOTE]
    >  Esta solución solo se puede usar si Visual Studio está instalado en el equipo de destino, o si desarrolla una herramienta personalizada.  
  
-   Compruebe el sistema lógico y los servicios de transmisión y recepción.  

## <a name="next-steps"></a>Pasos siguientes
[Usar el control de excepciones de BizTalk Server en la orquestación](../core/using-biztalk-server-exception-handling5.md)