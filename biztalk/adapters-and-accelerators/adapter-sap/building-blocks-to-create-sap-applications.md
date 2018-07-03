---
title: Bloques de creación para crear aplicaciones de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- design-time tasks
- run-time tasks
- developing, fundamentals of (BizTalk applications)
ms.assetid: 591a5597-5e7d-44b0-8bee-e1c987c5e6c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ff492d48538a54313d85202618e099e984fc3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006029"
---
# <a name="building-blocks-to-create-sap-applications"></a>Bloques de creación para crear aplicaciones de SAP
Realizar operaciones en un sistema SAP mediante [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] implica dos conjuntos de actividades: actividades de tiempo de diseño y tiempo de ejecución. Para realizar operaciones en un sistema SAP mediante la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe realizar un conjunto de tareas de tiempo de diseño y tiempo de ejecución mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, respectivamente. En esta sección se proporciona información general de estas tareas. Todos los temas de esta sección, que muestran cómo realizar operaciones específicas en un sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], se modelan en estas tareas de alto nivel.  
  
## <a name="design-time-tasks"></a>Tareas de tiempo de diseño  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona capacidad para examinar, buscar y recuperar los metadatos SAP para RFC, BAPI e IDOC en forma de lenguajes de definición de esquemas XML (XSD) mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]. El XSD es específicas de la operación que desea realizar en el sistema SAP, y el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] está disponible solo cuando se crea un proyecto de BizTalk. En tiempo de diseño necesario realizar las tareas siguientes.  
  
- **Crear proyecto de BizTalk y generar esquema**. Para empezar, debe crear un proyecto de BizTalk en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y generar el esquema para la solicitud de cambio invocará en el sistema SAP. Por ejemplo, si desea invocar RFC_CUSTOMER_GET en el sistema SAP, debe generar los metadatos para RFC_CUSTOMER_GET. En este paso utilizará el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema. Para obtener más información, consulte [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md).  
  
- **Configurar una orquestación**. Una vez que haya generado el esquema, debe configurar una orquestación mediante el Diseñador de orquestaciones. Para una orquestación básica, agregar el envío y recepción formas junto con el envío y recepción puertos lógicos. En pasos posteriores, puede asignar estos puertos lógicos a puertos físicos mediante la consola de administración de BizTalk Server. La orquestación usa estos puertos para seleccionar los mensajes que envía un cliente del adaptador. La orquestación, a continuación, pasa los mensajes al sistema SAP. Una vez que se recibe una respuesta desde el sistema SAP, la orquestación pasa la respuesta al cliente de adaptador.  
  
- **Crear mensajes y vincular al esquema**. En la orquestación, debe crear los mensajes que se asignará al esquema generado en el primer paso. Normalmente, se creación un mensaje de solicitud y un mensaje de respuesta. Estos mensajes se asignan a la solicitud correspondiente y esquemas de respuesta.  
  
- **Asignar formas de mensaje para mensajes y puertos**. En la orquestación, ahora debe asignar cada forma que agregó en el segundo paso para los mensajes que creó en el tercer paso. También se debe asignar una forma de mensaje al puerto en el que se envía ese mensaje.  
  
   Por ejemplo, si la primera forma en la orquestación es una forma recepción que recibe un mensaje, asignar esta forma a un mensaje de solicitud y el puerto que envía el mensaje de solicitud.  
  
- **Compilar e implementar el proyecto de BizTalk**. Después de configurar la orquestación y asigna los mensajes, puertos y los esquemas debe compilar la solución de BizTalk. Para compilar un proyecto [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], necesitará un archivo de clave de ensamblado. Después de crear correctamente la solución, debe implementar la solución.  
  
  > [!NOTE]
  >  Se proporciona una descripción más detallada de estas tareas de alto nivel, incluida la información de procedimientos, en distintos temas de esta sección.  
  
  Una vez implementada la solución, se llevan a cabo las tareas de tiempo de diseño. Ahora debe realizar las tareas de tiempo de ejecución.  
  
## <a name="run-time-tasks"></a>Tareas de tiempo de ejecución  
 En tiempo de ejecución, puede usar la consola de administración de BizTalk Server para implementar y supervisar la orquestación que creó en tiempo de diseño. Además, debe:  
  
- **Configurar la aplicación**. El proyecto de BizTalk que ha implementado en tiempo de diseño se muestra en la consola de administración de BizTalk Server como una orquestación. Debe configurar esta orquestación mediante la asignación de los puertos lógicos que creó en tiempo de diseño a puertos físicos que ahora debe crear mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
   En los puertos físicos, debe especificar una "acción" o "asignación de acciones". Esta acción corresponde a la operación que desea realizar en el sistema SAP. Debe establecer la acción si no usas acciones dinámicas. 
  
- **Inicie la aplicación**. Después de configura la aplicación, debe iniciar la aplicación y quitar mensajes de entrada en una ubicación de archivo definido. La orquestación consume los mensajes de entrada y los pasa al sistema SAP y recibe una respuesta. Esta respuesta estará disponible para usted en otra ubicación de archivo definido.  
  
  Para realizar estas tareas de tiempo de diseño y tiempo de ejecución de alto nivel, también debe realizar otras tareas. Por ejemplo, cuando usa el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema, debe especificar un URI de conexión para conectarse al sistema SAP. Esta sección proporciona información sobre las tareas repetitivas que debe realizar al desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)  
  
-   [Configurar el URI de conexión para el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)  
  
-   [Configurar el inicio de sesión en las credenciales para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md) 
  
-   [Configurar las propiedades de enlace para el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)
  
-   [Configurar la acción SOAP para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)
  
-   [Configurar manualmente un enlace de puerto físico para el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)
  
-   [Configurar un enlace de puerto físico mediante un archivo de enlace de puerto a SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)
  
-   [Configurar puertos dinámicos en el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)
  
-   [Volver a usar los enlaces del adaptador SAP](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de BizTalk con el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)