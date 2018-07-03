---
title: Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac7cbf4-b111-43ad-8726-36d037918c9c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96095b0d0b7df8dfabee1ff2a1955008bd757182
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975493"
---
# <a name="building-blocks-to-develop-biztalk-applications-with-the-sql-adapter"></a>Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL
Para realizar operaciones en SQL Server mediante el uso de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe realizar un conjunto de tareas de tiempo de diseño y tiempo de ejecución mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, respectivamente. En esta sección se proporciona información general de estas tareas. Todos los temas de esta sección, que muestran cómo realizar operaciones específicas en SQL Server mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], se modelan en estas tareas de alto nivel.  
  
## <a name="using-visual-studio"></a>Usar Visual Studio  
  
1. **Crear proyecto de BizTalk y generar esquema**. Debe crear un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y generar el esquema para la operación que llevará a cabo en SQL Server. Por ejemplo, si desea insertar registros en una tabla de SQL Server, debe generar el esquema para la operación de inserción para esa tabla. Para generar el esquema, se debe usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. Para obtener más información, consulte [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
2. **Configurar una orquestación**. Una vez que haya generado el esquema, debe configurar una orquestación mediante el Diseñador de orquestaciones. Para una orquestación básica, agregar el envío y recepción formas junto con el envío y recepción puertos lógicos. En pasos posteriores, puede asignar estos puertos lógicos a puertos físicos mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. La orquestación usa estos puertos para seleccionar los mensajes que envía un cliente del adaptador. La orquestación, a continuación, pasa los mensajes a SQL Server. Una vez que SQL Server envía una respuesta, la orquestación pasa la respuesta al cliente de adaptador.  
  
3. **Crear mensajes y vincular al esquema**. En la orquestación, debe crear los mensajes que se asignará al esquema generado en el primer paso. Normalmente, se creación un mensaje de solicitud y un mensaje de respuesta. Estos mensajes se asignan a los esquemas de respuesta y solicitud correspondiente.  
  
4. **Asignar formas de mensaje para mensajes y puertos**. En la orquestación, ahora debe asignar cada forma que agregó en el segundo paso para los mensajes que creó en el tercer paso. También se debe asignar una forma de mensaje al puerto en el que se envía ese mensaje.  
  
    Por ejemplo, si la primera forma en la orquestación es una forma recepción que recibirá un mensaje, asignar esta forma a un mensaje de solicitud y el puerto que envía el mensaje de solicitud.  
  
5. **Compilar e implementar el proyecto de BizTalk**. Una vez haya configurado la orquestación y mensajes asignados, los puertos y los esquemas, debe compilar la solución de BizTalk. Para compilar un proyecto [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], necesita un archivo de clave de ensamblado. Después de crear correctamente la solución, debe implementar la solución.  
  
> [!NOTE]
>  Se proporciona una descripción más detallada de estas tareas de alto nivel, incluida la información de procedimientos, en distintos temas de esta sección.  
  
 Una vez que ha creado e implementó el proyecto de BizTalk, las tareas en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se llevan a cabo. Ahora debe realizar determinadas tareas mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="using-the-biztalk-server-administration-console"></a>Utilizar la consola de administración de BizTalk Server  
  
1. **Configurar la aplicación**. El proyecto de BizTalk que se implementó mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se muestra en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración como una orquestación. Debe configurar esta orquestación mediante la asignación de los puertos lógicos que creó en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] a puertos físicos que ahora debe crear mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
    En los puertos físicos, debe especificar una "acción" o "asignación de acciones". Esta acción corresponde a la operación que desee realizar en SQL Server. Deberá especificar la acción si no usas acciones dinámicas. Para obtener más información acerca de las acciones, vea [configurar la acción SOAP para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).  
  
2. **Inicie la aplicación**. Después de configura la aplicación, debe iniciar la aplicación y eliminar mensajes de solicitud en una ubicación de archivo definido. La orquestación consume los mensajes de solicitud, pasa a SQL Server y recibe una respuesta. Esta respuesta está disponible para el cliente de adaptador en otra ubicación de archivo definido.  
  
   Para realizar estas tareas de alto nivel, también debe realizar otras tareas. Por ejemplo, cuando usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema, debe especificar un URI de conexión para conectarse a SQL Server. Esta sección proporciona información sobre las tareas repetitivas que debe realizar al desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Agregar el adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)  
  
-   [Configurar el URI de conexión del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-connection-uri-for-the-sql-adapter.md)  
  
-   [Configurar el inicio de sesión en las credenciales para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md)
  
-   [Configurar las propiedades de enlace del adaptador de SQL ](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md) 
  
-   [Configurar la acción SOAP para el adaptador de SQL ](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)
  
-   [Configurar manualmente un enlace de puerto físico al adaptador de SQL ](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md) 
  
-   [Configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)
  
-   [Configurar puertos dinámicos](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)
  
-   [Reutilizar los enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)