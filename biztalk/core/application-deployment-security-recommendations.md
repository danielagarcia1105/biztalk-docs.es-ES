---
title: Las recomendaciones de seguridad de implementación de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, applications
- best practices, applications
- best practices, security
- security, best practices
- applications, best practices
- applications, security
ms.assetid: 77902140-8b4c-437c-af4c-10a12b3bc950
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0402ef23de70150d541dfd672d2af7efe3a924
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231956"
---
# <a name="application-deployment-security-recommendations"></a>Recomendaciones de seguridad para implementación de aplicaciones
A continuación se presentan las directrices para implementar aplicaciones de BizTalk en el entorno:  
  
-   Todas las listas de control de acceso discrecional (DACL) se quitan de los archivos y carpetas cuando se exporta la aplicación a un archivo .msi. Tras instalar una aplicación del archivo .msi, debe volver a definir la configuración de seguridad de los archivos y carpetas.  
  
-   Por motivos de seguridad, cuando exporte un archivo de enlace, BizTalk Server quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción. Para obtener instrucciones, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Vea también [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md). Para obtener más información acerca de los archivos de enlace, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
-   Al implementar o anular la implementación de un esquema de propiedades, se pueden exponer datos confidenciales y, por lo tanto, información confidencial durante el seguimiento. Siempre que se implemente o se anule la implementación de un ensamblado que contenga un esquema de propiedades, el visor de eventos registrará un evento en el registro de eventos de aplicación de Windows. Debería comprobar el registro de eventos de estos mensajes para asegurarse de que todas las actividades de implementación de ensamblados están en línea con las directivas de datos confidenciales.  
  
     El mensaje que se genera en el registro de eventos de implementación es el siguiente:  
  
     **El usuario "{{1}" había implementado el ensamblado "{0}" que contiene esquemas de propiedad.**  
  
     El mensaje que se genera en el registro de eventos de anulación de implementación es el siguiente:  
  
     **El usuario "{{1}" anulado la implementación del ensamblado "{0}" que contiene esquemas de propiedad.**  
  
-   Si la aplicación incluye un directorio virtual, tenga en cuenta que la configuración de seguridad del directorio virtual es la que está activa cuando el archivo .msi se genera durante la exportación de la aplicación. Si implementa una aplicación en un entorno de producción, antes de exportar la aplicación debería comprobar que la configuración satisface los requisitos de seguridad.  
  
     Si, en cambio, implementa una aplicación que incluye un directorio virtual y éste ya existe en el entorno de destino, estará activa la configuración de seguridad del directorio virtual existente. No se modifica para que coincida con la del directorio virtual que va a implementar. Debería comprobar que la configuración de seguridad del directorio virtual existente cumple con los requisitos.  
  
    > [!CAUTION]
    >  Si el directorio virtual usa el protocolo HTTPS (Protocolo de transferencia de hipertexto a través de capa de sockets seguros), la configuración de seguridad no se mantiene durante la exportación y cuando se importa, el directorio virtual heredará la configuración de seguridad del elemento raíz. Debería comprobar que la configuración de seguridad cumple con los requisitos.  
  
-   Si el grupo de aplicaciones especificado para un servicio Web no existe cuando importa una aplicación, se utiliza el grupo de aplicaciones predeterminado. Es posible que la configuración de seguridad del grupo de aplicaciones predeterminado no sea adecuada para los requisitos. Por tanto, se recomienda que cree el grupo de aplicaciones y defina la configuración de seguridad adecuada antes de importar la aplicación, o bien compruebe que la configuración del grupo de aplicaciones predeterminado es la adecuada.  
  
-   Asegúrese de que el origen de los archivos (.msi) de Windows Installer que implementa es de confianza para evitar problemas de seguridad ocasionados por creadores de archivos .msi malintencionados. Para obtener más información, consulte [seguridad y Windows Installer](../core/security-and-windows-installer.md).  
  
-   Asegúrese de que tiene permisos para implementar aplicaciones. Para obtener más información, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
-   Asegúrese de que solo los administradores de BizTalk tienen acceso a los ensamblados, archivos de enlace y archivos de directiva, ya que pueden contener datos económicos importantes como información de conectividad y de configuración. Si implementa aplicaciones mediante un recurso compartido de red, configure la lista de control de acceso discrecional (DACL) en el recurso compartido de red para que solo los administradores de BizTalk puedan ver su contenido. Para obtener más información acerca de las cuentas de usuario y grupo, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
-   Cuando realiza operaciones de implementación, BizTalk Server se comunica con la base de datos de administración de BizTalk. Si existe un firewall entre ellos, debe abrir los puertos adecuados del firewall entre los dominios de procesamiento, de servicios y de datos. Para obtener más información, consulte [los puertos necesarios para que BizTalk Server](../core/required-ports-for-biztalk-server.md).  
  
-   Si selecciona una ubicación remota para un ensamblado, un archivo de enlace u otro archivo de recursos que pueda contener datos confidenciales, debería tener en cuenta la seguridad de red entre el equipo de origen y el equipo desde el que ejecuta la implementación. Si la red entre estos dos equipos no está aislada de posibles intrusos por completo, debería copiar el archivo de destino en medios extraíbles y transportarlo físicamente al equipo donde se ejecuta la implementación.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de seguridad para la implementación de aplicaciones](../core/security-considerations-for-application-deployment.md)