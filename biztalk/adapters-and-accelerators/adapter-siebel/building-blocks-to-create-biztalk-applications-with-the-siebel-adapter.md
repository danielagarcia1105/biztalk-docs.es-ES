---
title: Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing BizTalk applicatons, run-time tasks
- developing BizTalk applications, design-time tasks
ms.assetid: 76204181-18ad-43b5-b589-539aafd66835
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e457ec1eb3b3c79ef1fc1a4618bb6a0ef37755d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981973"
---
# <a name="building-blocks-to-create-biztalk-applications-with-the-siebel-adapter"></a>Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel
Realizar operaciones en un sistema de Siebel mediante [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] implica dos conjuntos de actividades: actividades de tiempo de diseño y tiempo de ejecución. Para realizar operaciones en un sistema de Siebel mediante el uso de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe realizar un conjunto de tareas de tiempo de diseño y tiempo de ejecución mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, respectivamente. En esta sección se proporciona información general de estas tareas. Todos los temas de esta sección, que muestran cómo realizar operaciones específicas en un sistema de Siebel mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], se modelan en estas tareas de alto nivel.  
  
## <a name="design-time-tasks"></a>Tareas de tiempo de diseño  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona la capacidad de explorar, buscar y recuperar los metadatos de Siebel de componentes empresariales y servicios empresariales en forma de lenguajes de definición de esquemas XML (XSD) mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. El XSD es específicas de la operación que desee realizar en el sistema de Siebel y la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] está disponible solo cuando se crea un proyecto de BizTalk. En tiempo de diseño debe realizar las siguientes tareas.  
  
- **Crear proyecto de BizTalk y generar esquema**. Para empezar, debe crear un proyecto de BizTalk en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y generar el esquema para los componentes empresariales o los servicios de negocios que invocará en el sistema Siebel. Por ejemplo, si desea insertar un registro en el componente de negocio de la cuenta, debe generar los metadatos de la operación de inserción para el componente de negocio de la cuenta. En este paso utilizará el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema. Para obtener más información, consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).  
  
- **Configurar una orquestación**. Una vez que haya generado el esquema, debe configurar una orquestación mediante el Diseñador de orquestaciones. Para una orquestación básica, agregar el envío y recepción formas junto con el envío y recepción puertos lógicos. En los pasos posteriores, asignará estos puertos lógicos a puertos físicos mediante la consola de administración de BizTalk Server. La orquestación usa estos puertos para recoger los mensajes enviados por un cliente del adaptador. La orquestación, a continuación, pasa los mensajes al sistema Siebel. Una vez que se recibe una respuesta desde el sistema de Siebel, la orquestación pasa la respuesta al cliente de adaptador.  
  
- **Crear mensajes y vincular al esquema**. En la orquestación, debe crear los mensajes que se asignará al esquema generado en el primer paso. Normalmente, crearía una solicitud y un mensaje de respuesta. Estos mensajes se asignan a la solicitud correspondiente y esquemas de respuesta.  
  
- **Asignar formas de mensaje para mensajes y puertos**. En la orquestación, ahora debe asignar cada forma que agregó en el segundo paso para los mensajes que creó en el tercer paso. También se debe asignar una forma de mensaje al puerto en el que se envía ese mensaje.  
  
   Por ejemplo, si la primera forma en la orquestación es una forma recepción que recibirá un mensaje, se asignará esta forma a un mensaje de "solicitud" y el puerto que envía el mensaje de solicitud.  
  
- **Compilar e implementar el proyecto de BizTalk**. Después de configurar la orquestación y asigna los mensajes, puertos y los esquemas debe compilar la solución de BizTalk. Para compilar un proyecto [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], necesitará un archivo de clave de ensamblado. Después de crear correctamente la solución, debe implementar la solución.  
  
  > [!NOTE]
  >  Una descripción de estas tareas de alto niveles más detallada, incluyendo información de procedimientos se proporciona en los temas siguientes.  
  
  Una vez implementada la solución, se llevan a cabo las tareas de tiempo de diseño. Ahora debe realizar las tareas de tiempo de ejecución.  
  
## <a name="run-time-tasks"></a>Tareas de tiempo de ejecución  
  
- **Configurar la aplicación**. El proyecto de BizTalk que ha implementado en tiempo de diseño se mostrará en la consola de administración de BizTalk Server como una orquestación. Debe configurar esta orquestación mediante la asignación de los puertos lógicos que creó en tiempo de diseño a puertos físicos que ahora debe crear mediante la consola de administración de BizTalk Server.  
  
   En los puertos físicos, debe especificar una "acción" o "asignación de acciones". Esta acción corresponde a la operación que desea realizar en el sistema Siebel. Debe establecer la acción si no usas acciones dinámicas. 
  
- **Inicie la aplicación**. Después de configura la aplicación, debe iniciar la aplicación y quitar mensajes de entrada en una ubicación de archivo definido. La orquestación consume los mensajes de entrada y los pasa al sistema Siebel y recibe una respuesta. Esta respuesta estará disponible para usted en otra ubicación de archivo definido.  
  
  Para realizar estas tareas de tiempo de diseño y tiempo de ejecución de alto nivel, también debe realizar otras tareas. Por ejemplo, cuando usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema, debe especificar un URI de conexión para conectarse al sistema Siebel. Esta sección proporciona información sobre las tareas repetitivas que debe realizar al desarrollar aplicaciones de BizTalk mediante el uso de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
