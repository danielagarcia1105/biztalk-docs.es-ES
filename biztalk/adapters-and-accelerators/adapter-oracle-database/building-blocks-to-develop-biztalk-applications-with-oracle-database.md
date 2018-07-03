---
title: Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, BizTalk applications
- run-time tasks
- design-time tasks
ms.assetid: ad9ca856-5569-41ab-8617-ae6db5e3b4d7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703bff35321fcedb4240d8ced1f422707c0ca51e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973805"
---
# <a name="building-blocks-to-develop-biztalk-applications-with-oracle-database"></a>Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle
Realizar operaciones en una base de datos de Oracle mediante el uso de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] implica dos conjuntos de tareas: tiempo de diseño y tiempo de ejecución.  
  
## <a name="design-time-tasks"></a>Tareas de tiempo de diseño  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona capacidad para examinar, buscar y recuperar los metadatos de Oracle para tablas, procedimientos almacenados y otros elementos de este tipo en forma de lenguajes de definición de esquemas XML (XSD) mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]. El XSD es específicos de la operación que desee realizar en la base de datos de Oracle. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] está disponible solo cuando se crea un proyecto de BizTalk. En tiempo de diseño deberá realizar las siguientes tareas:  
  
- **Crear proyecto de BizTalk y generar esquema**. Debe crear un proyecto de BizTalk en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y generar el esquema para la operación que se realizará en la base de datos de Oracle. Por ejemplo, si desea insertar un registro en la tabla de empleados, debe generar los metadatos de la operación de inserción para la tabla EMPLOYEE. En este paso, utilizará el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Para obtener más información, consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).
  
- **Configurar una orquestación**. Una vez que haya generado el esquema, debe configurar una orquestación mediante el Diseñador de orquestaciones. Para una orquestación básica, agregar el envío y recepción formas junto con el envío y recepción puertos lógicos. En pasos posteriores, puede asignar estos puertos lógicos a puertos físicos mediante la consola de administración de BizTalk Server. La orquestación usa estos puertos para seleccionar los mensajes que envía un cliente del adaptador. La orquestación, a continuación, pasa los mensajes a la base de datos de Oracle. Una vez que se recibe una respuesta de la base de datos de Oracle, la orquestación pasa la respuesta al cliente de adaptador.  
  
- **Crear mensajes y vincular al esquema**. En la orquestación, debe crear los mensajes que se asignará al esquema generado en el primer paso. Normalmente, se creación un mensaje de solicitud y un mensaje de respuesta. Estos mensajes se asignan a la solicitud correspondiente y esquemas de respuesta.  
  
- **Asignar formas de mensaje para mensajes y puertos**. En la orquestación, ahora debe asignar cada forma que agregó en el segundo paso para los mensajes que creó en el tercer paso. También se debe asignar una forma de mensaje al puerto en el que se envía ese mensaje.  
  
   Por ejemplo, si la primera forma en la orquestación es una forma recepción que recibirá un mensaje, asignar esta forma a un mensaje de solicitud y el puerto que envía el mensaje de solicitud.  
  
- **Compilar e implementar el proyecto de BizTalk**. Una vez haya configurado la orquestación y mensajes asignados, los puertos y los esquemas, debe compilar la solución de BizTalk. Para compilar un proyecto [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], necesita un archivo de clave de ensamblado. Después de crear correctamente la solución, debe implementar la solución.  
  
  > [!NOTE]
  >  Se proporciona una descripción más detallada de estas tareas de alto nivel, incluida la información de procedimientos, en distintos temas de esta sección.  
  
  Una vez implementada la solución, se llevan a cabo las tareas de tiempo de diseño. Ahora debe realizar las tareas de tiempo de ejecución.  
  
## <a name="run-time-tasks"></a>Tareas de tiempo de ejecución  
 En tiempo de ejecución, puede usar la consola de administración de BizTalk Server para implementar y supervisar la orquestación que creó en tiempo de diseño. Además, debe:  
  
- **Configurar la aplicación**. El proyecto de BizTalk que ha implementado en tiempo de diseño se muestra en la consola de administración de BizTalk Server como una orquestación. Debe configurar esta orquestación mediante la asignación de los puertos lógicos que creó en tiempo de diseño a puertos físicos que ahora debe crear mediante la consola de administración de BizTalk Server.  
  
   En los puertos físicos, debe especificar una "acción" o "asignación de acciones". Esta acción corresponde a la operación que desee realizar en la base de datos de Oracle. Debe establecer la acción si no usas acciones dinámicas.  
  
- **Inicie la aplicación**. Después de configura la aplicación, debe iniciar la aplicación y quitar mensajes de entrada en una ubicación de archivo definido. La orquestación consume los mensajes de entrada y pasa a la base de datos de Oracle y recibe una respuesta. Esta respuesta estará disponible para usted en otra ubicación de archivo definido.  
  
  Para realizar estas tareas de tiempo de diseño y tiempo de ejecución de alto nivel, también debe realizar otras tareas. Por ejemplo, cuando usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar el esquema, debe especificar un URI de conexión para conectarse a la base de datos de Oracle. Esta sección proporciona información sobre las tareas repetitivas que debe realizar al desarrollar aplicaciones de BizTalk con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  

  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)