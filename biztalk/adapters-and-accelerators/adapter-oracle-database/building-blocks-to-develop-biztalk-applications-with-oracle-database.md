---
title: "Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, BizTalk applications
- run-time tasks
- design-time tasks
ms.assetid: ad9ca856-5569-41ab-8617-ae6db5e3b4d7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0747569ef58e1f2223baefba6c51b77b205eb0d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="building-blocks-to-develop-biztalk-applications-with-oracle-database"></a>Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle
Realizar operaciones en una base de datos de Oracle mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] implica dos conjuntos de tareas: tiempo de diseño y tiempo de ejecución.  
  
## <a name="design-time-tasks"></a>Tareas de tiempo de diseño  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona capacidad para examinar, buscar y recuperar los metadatos de Oracle para tablas, procedimientos almacenados y otros elementos en forma de lenguajes de definición de esquemas XML (XSD) de este tipo mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]. El XSD es específicos de la operación que desea realizar en la base de datos de Oracle. La [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] está disponible solo cuando se crea un proyecto de BizTalk. En tiempo de diseño debe realizar las siguientes tareas:  
  
-   **Crear proyecto de BizTalk y generar esquema**. Debe crear un proyecto de BizTalk en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y generar el esquema para la operación que se realizará en la base de datos de Oracle. Por ejemplo, si desea insertar un registro en la tabla de empleados, debe generar los metadatos de la operación de inserción para la tabla EMPLOYEE. En este paso, usará el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema. Para obtener más información, consulte [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).
  
-   **Configurar una orquestación**. Una vez que haya generado el esquema, debe configurar una orquestación mediante el Diseñador de orquestaciones. Para una orquestación básica, agregar el envío y recepción formas junto con el envío y puertos lógicos de recepción. En pasos posteriores, se asignan estos puertos lógicos a puertos físicos mediante la consola de administración de BizTalk Server. La orquestación usa estos puertos para seleccionar los mensajes que envía un cliente de adaptador. La orquestación, a continuación, pasa los mensajes a la base de datos de Oracle. Una vez que se recibe una respuesta de la base de datos de Oracle, la orquestación pasa la respuesta al cliente de adaptador.  
  
-   **Crear mensajes y vincular al esquema**. En la orquestación, debe crear mensajes que se va a asignar el esquema generado en el primer paso. Normalmente, se crean un mensaje de solicitud y un mensaje de respuesta. Estos mensajes se asignan a correspondiente esquemas de solicitud y respuesta.  
  
-   **Formas de mensaje se asignan a los mensajes y puertos**. En la orquestación, a continuación, debe asignar cada forma que agregó en el segundo paso para mensajes que creó en el tercer paso. También se debe asignar una forma de mensaje al puerto en el que se enviará el mensaje.  
  
     Por ejemplo, si la primera forma en la orquestación es una forma recepción que recibirá un mensaje, asignar esta forma a un mensaje de solicitud y el puerto que envía el mensaje de solicitud.  
  
-   **Compilar e implementar el proyecto de BizTalk**. Una vez haya configurado la orquestación y mensajes asignados, puertos y esquemas, debe generar la solución de BizTalk. Para compilar un proyecto en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], necesitará un archivo de clave de ensamblado. Después de crear correctamente la solución, debe implementar la solución.  
  
    > [!NOTE]
    >  Se proporciona una descripción más detallada de estas tareas de alto nivel, incluida la información de procedimientos, de varios temas de esta sección.  
  
 Una vez que se implementa la solución, se llevan a cabo las tareas de tiempo de diseño. Ahora, debe realizar las tareas de tiempo de ejecución.  
  
## <a name="run-time-tasks"></a>Tareas de tiempo de ejecución  
 En tiempo de ejecución, puede utilizar la consola de administración de BizTalk Server para implementar y supervisar la orquestación creada en tiempo de diseño. Además, debe:  
  
-   **Configurar la aplicación**. El proyecto de BizTalk que implementó en tiempo de diseño se muestra en la consola de administración de BizTalk Server como una orquestación. Debe configurar esta orquestación mediante la asignación de los puertos lógicos que creó en tiempo de diseño a puertos físicos que ahora debe crear mediante la consola de administración de BizTalk Server.  
  
     En los puertos físicos, debe especificar una "acción" o "asignación de acciones". Esta acción corresponde a la operación que desea realizar en la base de datos de Oracle. Debe establecer la acción si no usas acciones dinámicas.  
  
-   **Inicie la aplicación**. Después de configura la aplicación, debe iniciar la aplicación y eliminar mensajes de entrada en una ubicación de archivo definido. La orquestación consume los mensajes de entrada y los pasa a la base de datos de Oracle y recibe una respuesta. Esta respuesta estará disponible para usted en otra ubicación de archivo definido.  
  
 Para realizar estas tareas de tiempo de diseño y tiempo de ejecución de alto nivel, también debe realizar otras tareas. Por ejemplo, cuando usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar el esquema, debe especificar un URI de conexión para conectarse a la base de datos de Oracle. Esta sección proporciona información sobre las tareas repetitivas que debe realizar cuando desarrolle aplicaciones de BizTalk con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  

  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)