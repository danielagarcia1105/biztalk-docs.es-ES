---
title: "Bloques de creación para crear aplicaciones de Oracle E-Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 483a52d4-1aaf-46b1-bb42-9f91bf678346
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0450f672573153df803f875a0dbac1436f8f4760
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="building-blocks-to-create-oracle-e-business-suite-applications"></a>Bloques de creación para crear aplicaciones de Oracle E-Business Suite
Para realizar operaciones en Oracle E-Business Suite mediante el uso de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe realizar un conjunto de tareas de tiempo de diseño y tiempo de ejecución mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] respectivamente de consola de administración. Esta sección proporciona información general sobre estas tareas. Todos los temas de esta sección, que muestran cómo realizar operaciones específicas sobre el uso de Oracle E-Business Suite [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], se modelan en estas tareas de alto nivel.  
  
## <a name="using-visual-studio"></a>Usar Visual Studio  
  
1.  **Crear proyecto de BizTalk y generar esquema**. Debe crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y generar el esquema para la operación que llevará a cabo en Oracle E-Business Suite. Por ejemplo, si desea seleccionar los registros de una tabla de la interfaz de Oracle E-Business Suite, debe generar el esquema para la operación de selección para la tabla. Para generar el esquema, se debe usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Para obtener más información, consulte [recuperación de metadatos para las operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
2.  **Configurar una orquestación**. Una vez que haya generado el esquema, debe configurar una orquestación mediante el Diseñador de orquestaciones. Para una orquestación básica, agregar el envío y recepción formas junto con el envío y puertos lógicos de recepción. En pasos posteriores, puede asignar estos puertos lógicos a puertos físicos mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. La orquestación usa estos puertos para seleccionar los mensajes que envía un cliente de adaptador. La orquestación, a continuación, pasa los mensajes a Oracle E-Business Suite. Una vez que Oracle E-Business Suite envía una respuesta, la orquestación pasa la respuesta al cliente de adaptador.  
  
3.  **Crear mensajes y vincular al esquema**. En la orquestación, debe crear mensajes que se va a asignar el esquema generado en el primer paso. Normalmente, se crean un mensaje de solicitud y un mensaje de respuesta. Estos mensajes se asignan a los esquemas de respuesta y solicitud correspondiente.  
  
4.  **Formas de mensaje se asignan a los mensajes y puertos**. En la orquestación, a continuación, debe asignar cada forma que agregó en el segundo paso para mensajes que creó en el tercer paso. También se debe asignar una forma de mensaje al puerto en el que se enviará el mensaje.  
  
     Por ejemplo, si la primera forma en la orquestación es una forma recepción que recibirá un mensaje, asignar esta forma a un mensaje de solicitud y el puerto que envía el mensaje de solicitud.  
  
5.  **Compilar e implementar el proyecto de BizTalk**. Una vez haya configurado la orquestación y mensajes asignados, puertos y esquemas, debe generar la solución de BizTalk. Para compilar un proyecto en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], necesitará un archivo de clave de ensamblado. Después de crear correctamente la solución, debe implementar la solución.  
  
> [!NOTE]
>  Se proporciona una descripción más detallada de estas tareas de alto nivel, incluida la información de procedimientos, de varios temas de esta sección.  
  
 Una vez correctamente ha creado e implementado el proyecto de BizTalk, el tiempo de diseño las tareas de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se llevan a cabo. Ahora se deben realizar ciertas tareas de tiempo de ejecución mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="using-the-biztalk-server-administration-console"></a>Utilizar la consola de administración de BizTalk Server  
  
1.  **Configurar la aplicación**. El proyecto de BizTalk que se ha implementado mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se muestra en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración como una orquestación. Debe configurar esta orquestación mediante la asignación de los puertos lógicos que creó en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] a puertos físicos que ahora debe crear mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
     En los puertos físicos, debe especificar una "acción" o "asignación de acciones". Esta acción corresponde a la operación que desea realizar en Oracle E-Business Suite. Debe especificar la acción si no usas acciones dinámicas. Para obtener más información acerca de las acciones, vea [configurar la acción SOAP para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md).  
  
2.  **Inicie la aplicación**. Después de configura la aplicación, debe iniciar la aplicación y eliminar mensajes de solicitud en una ubicación de archivo definido. La orquestación consume los mensajes de solicitud, pasa a Oracle E-Business Suite y recibe una respuesta. Esta respuesta está disponible para el cliente del adaptador en otra ubicación de archivo definido.  
  
 Para realizar estas tareas de alto nivel, también debe realizar otras tareas. Por ejemplo, cuando usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema, debe especificar un URI de conexión para conectarse a Oracle E-Business Suite. Esta sección proporciona información sobre las tareas repetitivas que debe realizar cuando desarrolle aplicaciones de BizTalk con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Agregar el adaptador de Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)  
  
-   [Configurar el URI de conexión para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)  
  
-   [Configurar las credenciales de inicio de sesión para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)  
  
-   [Configurar las propiedades de enlace para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)  
  
-   [Configurar la acción SOAP para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)  
  
-   [Configuración manual de un puerto físico de enlace para el adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  
  
-   [Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)  
  
-   [Configurar puertos dinámicos con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-dynamic-ports-with-oracle-e-business-suite.md)  
  
-   [Reutilizar los enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de aplicaciones de BizTalk](../../core/developing-biztalk-server-applications.md)