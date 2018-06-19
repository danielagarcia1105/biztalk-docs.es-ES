---
title: 'Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a9de95f-7d2c-437d-be5b-0062592f32c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c11b163f34a1320052de585c7ddfc79afb03db4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287348"
---
# <a name="tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013"></a>Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013
Esta sección proporciona procedimientos detallados sobre cómo crear una aplicación híbrida que incluya [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="business-scenario"></a>Escenario de negocio  
 Northwind es una empresa que recibe pedidos de ventas de sus socios (uno de los cuales es Contoso) en forma de mensajes EDI de archivo sin formato. Northwind quiere configurar una aplicación de extremo a extremo que realice lo siguiente:  
  
-   **Administrar el procesamiento de mensajes EDI** : este módulo de la aplicación debe comprobar que el mensaje recibido de Contoso se ajusta a los formatos de mensaje EDI estándares. Este módulo también debe generar todas las confirmaciones necesarias para comprobar que el mensaje se procesa correctamente.  
  
-   **Usar lógica de negocios para procesar los datos** : una vez que el mensaje EDI está comprobado y se procesa correctamente, Northwind debe ejecutar el mensaje en la lógica de negocios para su posterior procesamiento. Por ejemplo, si la cantidad del pedido en el mensaje recibido es superior a la cantidad proporcionada, los datos se almacenan en una base de datos de SQL Server. En caso contrario, los datos se envían a una ubicación de archivo compartida.  
  
 Para lograr este escenario, Northwind decide configurar una aplicación híbrida en la que el procesamiento de mensajes EDI se realice en la nube mientras el procesamiento de datos controlado por la lógica empresarial se realiza en las instalaciones. Para configurar esta aplicación híbrida, Northwind usa lo siguiente:  
  
-   **[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]** El Portal de Azure BizTalk disponible con [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] permite a los clientes configurar socios comerciales y acuerdos EDI en [!INCLUDE[winazure](../includes/winazure-md.md)]. Northwind usa la versión de [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] de abril de 2012 para crear e implementar un acuerdo que procese el mensaje EDI entrante, lo valide con el esquema de pedidos de ventas X12 840, transforme el mensaje en un esquema que necesita Northwind y lo envíe a una cola de Service Bus. Así, para desarrollar una aplicación híbrida, los datos deberían enviarse desde la cola de Service Bus a una aplicación local.  
  
-   **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**: El nuevo adaptador de Bus de servicio (**SB-Messaging**) disponible con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite a las aplicaciones recibir mensajes de entidades de Service Bus como colas, temas, y así sucesivamente en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Como parte de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] aplicación, Northwind usa una orquestación para decidir si la cantidad solicitada en el pedido de ventas recibido es superior a 100. Si la cantidad es mayor que 100, el mensaje se inserta en una tabla de base de datos de SQL Server denominada **SalesOrder**. Si la cantidad es inferior a 100, el mensaje se envía a una ubicación de archivo compartida.  
  
     Para insertar el mensaje en una tabla de base de datos de SQL Server, Northwind usa el [!INCLUDE[adaptersql](../includes/adaptersql-md.md)] disponible como parte de [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
### <a name="end-to-end-message-flow"></a>Flujo de mensajes de extremo a extremo  
 El mensaje fluye por la aplicación híbrida del modo siguiente:  
  
1.  Contoso envía un mensaje de pedido de ventas de X12 al extremo en el que se implementa el acuerdo de EDI en la nube.  
  
2.  Una vez procesado correctamente el mensaje a través del acuerdo EDI, se envía a la cola de Service Bus.  
  
3.  El adaptador de recepción de SB-Messaging consume el mensaje desde la cola de Service Bus e instancia la orquestación implementada en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enviar el mensaje a distintos destinos en función de la cantidad del pedido.  
  
4.  Si la cantidad pedida es superior a 100, la orquestación inserta el mensaje en una **SalesOrder** tabla. Si la cantidad solicitada es inferior o igual a 100, el mensaje se escribe en una ubicación de archivo compartida.  
  
## <a name="set-up-your-computer"></a>Configurar el PC  
 Este tutorial requiere que realice cuatro actividades. La siguiente tabla muestra las actividades y los requisitos de software para cada una de ellas:  
  
|Actividad|Software necesario|  
|--------------|-----------------------|  
|Crear artefactos de EDI necesarios para el acuerdo de EDI|Este tutorial se ha creado con la versión de [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] de abril de 2012 y el esquema de pedidos de ventas X12 840. Puede descargarlo desde [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).|  
|Crear e implementar el acuerdo de EDI|Dado que el acuerdo de EDI se implementa en Azure, solo necesita un explorador web (por ejemplo, Internet Explorer) para iniciar sesión en el portal Azure de BizTalk.|  
|Crear, implementar y configurar la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|Si desea aprovisionar un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo en una máquina virtual de Azure, siga las instrucciones de [http://msdn.microsoft.com/library/azure/jj248689.aspx](http://msdn.microsoft.com/library/azure/jj248689.aspx).|  
|Enviar un mensaje de prueba al extremo del acuerdo de EDI|Puede usar la herramienta MessageSender disponible en el paquete de pruebas proporcionado con [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]. Puede descargar el paquete de ejemplos de [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).|  
  
 Puede optar por instalar todo en el mismo PC o en PCs diferentes.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1 (para Azure): Crear el proyecto EDI](../core/step-1-for-azure-create-the-edi-project.md)  
  
-   [Paso 2 (para Azure): Crear un acuerdo de EDI](../core/step-2-for-azure-create-an-edi-agreement.md)  
  
-   [Paso 3 (para Azure): Crear una cola de Bus de servicio](../core/step-3-for-azure-create-a-service-bus-queue.md)  
  
-   [Paso 4 (de forma local): Crear la tabla de SQL Server](../core/step-4-on-premises-create-the-sql-server-table.md)  
  
-   [Paso 5 (local): Generar el esquema para insertar un mensaje en la tabla SalesOrder](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)  
  
-   [Paso 6 (de forma local): Crear una transformación para asignar el mensaje de la cola en el esquema de inserción](../core/step-6-map-the-message-from-the-queue-to-the-insert-schema.md)  
  
-   [Paso 7 (de forma local): Crear una orquestación](../core/step-7-on-premises-create-an-orchestration.md)  
  
-   [Paso 8 (de forma local): Configurar la aplicación de BizTalk Server](../core/step-8-on-premises-configure-the-biztalk-server-application.md)  
  
-   [Paso 9: Probar la solución](../core/step-9-test-the-solution.md)