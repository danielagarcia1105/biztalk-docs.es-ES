---
title: "Problemas conocidos con la instalación, configuración e implementación de soluciones EDI y AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dee03f0-2447-4cc2-90f4-e9b73caa0f39
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 406e69cafd4822a0f8f436b471d53c4e815dce32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a>Problemas conocidos con la instalación, configuración e implementación de soluciones EDI y AS2
En este tema se describen los problemas conocidos relacionados con la implementación y administración de soluciones EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="blank-strings-were-imported-for-party-properties"></a>Se han importado cadenas en blanco para las propiedades de entidades.  
 **Síntoma**  
  
 Cuando importó enlaces EDI/AS2 de un archivo de enlace a una aplicación de BizTalk, las propiedades con distinción de entidad, como contraseñas o información de seguridad/autenticación, no se importaron. Esas propiedades estaban establecidas como cadenas en blanco.  
  
 **Causa posible**  
  
 BizTalk Server no importará la configuración de campos con distinción. La importación de esta configuración podría provocar un problema de seguridad.  
  
 **Resolución**  
  
 Tras importar los enlaces en otro equipo, debe establecer manualmente los valores de los campos con distinción de EDI.  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a>El adaptador de FTP no es compatible de forma nativa con el modo de 64 bits.  
 El adaptador de FTP no se puede ejecutar en el modo nativo de 64 bits. Si usa un adaptador de FTP en la solución EDI en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], deberá ejecutarlo en WOW64 en la versión de 64 bits de Windows.  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a>Algunos artefactos de EDI y AS2 siguen activos después de quitar la configuración  
 Tras quitar la configuración de la característica EDI y AS2 de Microsoft de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], algunos artefactos de BizTalk Server relacionados con el procesamiento de EDI y AS2 seguirán activos en el contexto de la configuración de grupos de BizTalk. Estos artefactos incluirán las canalizaciones EDI y AS2 y la orquestación de procesamiento por lotes. Como resultado, seguirá pudiendo realizar un procesamiento básico de EDI y AS2 incluso después de haber quitado la configuración de la característica de EDI y AS2 de Microsoft. Para desactivar esta funcionalidad, debe deshabilitar, detener o eliminar los puertos asociados con el procesamiento de EDI y AS2.  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a>Recibe el error "No se pudieron configurar las funcionalidades del informe de estado de EDI y AS2"  
 **Síntoma**  
  
 Al configurar informes de estado de tiempo de ejecución de EDI y AS2, recibe el error "No se pudieron configurar las funcionalidades del informe de estado de EDI y AS2".  
  
 **Causa posible**  
  
 Puede recibir este error si las herramientas de BAM estaban configuradas anteriormente y después se les ha quitado la configuración.  
  
 **Resolución**  
  
 Configure las herramientas de BAM antes de configurar los informes de estado de EDI y/o AS2.  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a>La recuperación de un artefacto eliminado de la aplicación EDI de BizTalk requiere que se vuelva a configurar el tiempo de ejecución de EDI y AS2.  
 Debe evitar usar la aplicación EDI de BizTalk para sus propios artefactos. Esta aplicación contiene los artefactos de EDI y AS2 implementados durante la configuración de EDI y AS2. El enfoque recomendado es crear una aplicación independiente y agregar una referencia de la aplicación EDI de BizTalk a su aplicación. No obstante, si elimina algún artefacto de EDI o AS2 de la aplicación EDI de BizTalk, puede recuperarlo desde ese estado quitando la configuración del tiempo de ejecución de EDI o AS2 de BizTalk de cada equipo de tiempo de ejecución del grupo (o quitando la configuración del tiempo de ejecución de EDI o AS2 de cada equipo de tiempo de ejecución accesible). Se recomienda no eliminar las bases de datos o las actividades de BAM de EDI/AS2 para evitar pérdidas de datos. Puede volver a configurar el tiempo de ejecución de EDI/AS2 en todos los equipos de tiempo de ejecución del grupo para recuperar los artefactos EDI/AS2 eliminados.  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a>Es posible que se trunquen los valores de control de intercambio, control de grupo y conjunto de transacciones numéricos  
 Los campos de rangos de valores para números de control de intercambio, números de referencia de conjuntos de transacciones y números de control de grupos permiten especificar valores que sobrepasan el valor máximo permitido. Al guardar la configuración, estos valores se truncarán al valor máximo.  
  
 El valor máximo de los campos de propiedades de X12 es 999999999.  
  
 El valor máximo de los campos de propiedades de EDIFACT es 99999999999999.  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a>Los números de control se restablecen en 1 después de la actualización  
 Después de actualizar, puede observar que todos los números de control que se muestran en las propiedades de EDI de una entidad se haya restablecido al valor mínimo predeterminado de 1 y mostrar el valor máximo predeterminado de 999999999 (X12) o 99999999999999 (EDIFACT). Los valores de prefijo o sufijo permanecerán igual después de la actualización.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Muestra los valores mínimos y máximo que se usará para el número de control. El número de control actual se conservarán durante la actualización; Sin embargo no se muestra en las propiedades de EDI de la entidad.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md)   
 [Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [Introducción a la configuración de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)   
 [Pasos posteriores a la configuración para optimizar el entorno](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)