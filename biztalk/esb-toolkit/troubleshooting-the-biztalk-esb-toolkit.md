---
title: Solución de problemas del Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
description: Solucionar problemas de instalación y errores comunes con el Kit de herramientas de ESB en BizTalk Server
caps.latest.revision: 2
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ea2d56-2ace-40f2-80df-8a7489bbfc2e
ms.author: mandia
ms.openlocfilehash: 8fc1305e481de2444a54ea994f8a53da83b2eaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295348"
---
# <a name="troubleshoot-the-biztalk-esb-toolkit"></a>Solucionar problemas del Kit de herramientas de ESB de BizTalk

  
## <a name="installation"></a>Installation  
  
|Problema|Solución|  
|-----------|----------------|  
|Se generará una excepción de "Error al asignar permisos" durante la instalación.|El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] usa los grupos de cuentas de BizTalk estándares, que deben existir durante el proceso de instalación o la instalación se producirá un error. Además, se da por supuesto en el Kit de herramientas de una instalación independiente en el equipo es miembro de un grupo de trabajo o una instalación de enterprise donde el equipo es un miembro de un dominio.|  
|Se produce un error en la importación de la aplicación con un mensaje de error que advierte de no coincidencia de nivel de confianza.|Los archivos de enlace Microsoft.BizTalk.ESB se configuran para trabajar con el valor predeterminado BizTalkServerApplication y BizTalkServerIsolatedHost, que a su vez están configurados para ejecutarse en modo de confianza. Si ha cambiado el host para que se ejecute en modo de confianza, no se importará el archivo de enlace. Para corregir este problema, debe cambiar el nivel de confianza para que no se confía o edite el archivo de enlace para adaptarlas a su entorno en el directorio de \Bindings BizTalk Toolkit.|  
|La autenticación Kerberos no está configurada en Internet Information Services (IIS).|Para habilitar la autenticación Kerberos para IIS, vea los siguientes artículos de Microsoft Knowledge Base:<br /><br /> -   [Cómo configurar IIS para que admita el protocolo Kerberos y el protocolo NTLM para la autenticación de red](http://go.microsoft.com/fwlink/?LinkId=188566)<br />-   [Cómo habilitar IIS para usar la autenticación Kerberos en un equipo que no sea un controlador de dominio](http://go.microsoft.com/fwlink/?LinkId=188567)<br />-   [No se puede configurar los protocolos NTLM o Negotiate para la autenticación integrada de Windows en el Administrador de IIS para servicios de Internet Information Server (IIS) 7.0](http://go.microsoft.com/fwlink/?LinkId=188568)|  
  
## <a name="general-issues"></a>Problemas generales  
  
|Problema|Solución|  
|-----------|----------------|  
|Recibirá una excepción "Procesamiento de SOAP interno" al enviar un mensaje al servicio Web de ESB itinerario en rampa genérico.|Usar la consola de administración de BizTalk Server para asegurarse de que se está ejecutando la aplicación Microsoft.Practices.ESB; Si no se está ejecutando, inícielo.|  
|Mensajes de excepción no aparecen en el sitio del Portal de administración de ESB.|Compruebe la página información general de grupo de administrador de BizTalk y el registro de eventos de aplicación de Windows para las entradas que indican errores al enviar mensajes. Debe volver a configurar la excepción: adaptador de envío (parte de la aplicación Microsoft.Practices.ESB) para que coincida con su entorno. Además, tenga en cuenta que la característica de enrutamiento de mensajes de error de BizTalk y el marco de trabajo de administración de BizTalk ESB Toolkit excepción generan mensajes de excepciones. Por lo tanto, asegúrese de que habilita la **ruta en los mensajes de error** opción de envío y puertos de recepción.|  
|Al consumir un servicio WCF con una resolución estática, recibirá una excepción de acción SOAP no válida.|Si la acción de SOAP del servicio WCF no incluye el espacio de nombres de destino, establezca el valor de la acción SOAP en el siguiente formato en la configuración de resolución: {action} para indicar que el espacio de nombres de destino no se concatenarán por el motor en tiempo de ejecución principal del Kit de herramientas ESB.|