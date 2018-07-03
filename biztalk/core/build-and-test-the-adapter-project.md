---
title: Compilar y probar el proyecto de adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b5eb486-99ae-4661-b0d0-d2d363d97b73
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69f499a3d3dd3bced347525ed91b5a28d2490b59
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005813"
---
# <a name="build-and-test-the-adapter-project"></a>Generar y probar el proyecto de adaptador
Para probar todos los cambios realizados en el proyecto AdapterManagement, vuelva a generar el proyecto. Después de realizar una generación correcta, ejecute el Asistente para agregar metadatos de adaptador para asegurarse de que todos los archivos XSD internos y externos se agreguen al proyecto AdapterManagement. Para obtener instrucciones sobre cómo utilizar el Asistente para agregar metadatos de adaptador, vea [cómo agregar metadatos de adaptador a un proyecto de BizTalk](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md).  

 Para probar los cambios realizados en los esquemas de configuración, abra cada una de las páginas de propiedades generadas por el archivo XSD para asegurarse de que pida y acepte los datos correctos. Hacer esto mediante la configuración de un puerto de envío, ubicación de recepción, controlador de envío y controlador de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración<strong>.</strong>  

> [!NOTE]
>  Es posible que un adaptador no tenga todos los esquemas de configuración. Por ejemplo, un adaptador de envío que no admita la recepción de mensajes podría tener únicamente los esquemas TransmitLocation.xsd y TransmitHandler.xsd.  

### <a name="to-test-the-transmitlocationxsd-file"></a>Para probar el archivo TransmitLocation.xsd  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. Expanda el [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración** nodo, expanda **grupo de BizTalk**, expanda el **puertos de envío** nodo, seleccione **New**, y a continuación, haga clic en **puerto de envío unidireccional estático**.  

3. En el **propiedades de puerto de envío** cuadro de diálogo el **nombre** , escriba el nombre del puerto de envío. Expanda el **transporte** nodo y, a continuación, seleccione el **principal** nodo.  

4. En el panel derecho, en el **el valor de tipo de transporte** cuadro, seleccione **estático**y, a continuación, haga clic en **configurar**. La pantalla mostrada debe contener los campos especificados en el archivo TransmitLocation.xsd.  

### <a name="to-test-the-receivelocationxsd-file"></a>Para probar el archivo ReceiveLocation.xsd  

1. Expanda el [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración** nodo, expanda **grupo de BizTalk**, expanda el **puertos de recepción** colección, expanda acaba de crear el puerto de recepción o el puerto de recepción al que desea agregar una ubicación de recepción, haga clic en el **ubicaciones de recepción** colección, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  

2. En el **seleccionar un puerto de recepción** cuadro de diálogo, seleccione el puerto.  

3. En el **propiedades de ubicación de recepción** cuadro de diálogo, en el panel izquierdo, seleccione el **General** nodo.  

4. En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba un nombre para la ubicación de recepción.  

5. En el **propiedades de ubicación de recepción** cuadro de diálogo, en el panel derecho, el **el valor de tipo de transporte** cuadro, seleccione **estático** y, a continuación, haga clic en **configurar**. La pantalla mostrada debe contener los campos especificados en el archivo ReceiveLocation.xsd.  

### <a name="to-test-the-receivehandlerxsd-file"></a>Para probar el archivo ReceiveHandler.xsd  

1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. Expanda el [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración** nodo, expanda **grupo de BizTalk,** expanda **configuración de plataforma**, expanda **adaptadores**, Haga clic en **estático**y, a continuación, haga clic en **BizTalkServerApplication** con la dirección de **recepción**.  

3. En el panel de resultados, haga clic en el controlador de recepción y, a continuación, haga clic en **propiedades**. En el **General** , haga clic **propiedades**. La pantalla mostrada debe contener los campos especificados en el archivo ReceiveHandler.xsd.  

### <a name="to-test-the-transmithandlerxsd-file"></a>Para probar el archivo TransmitHandler.xsd  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **estático**y, a continuación, haga clic en **BizTalkServerApplication** con la dirección de **enviar**.  

2. En el panel de resultados, haga clic en el controlador de recepción y, a continuación, haga clic en **propiedades**. En el **General** , haga clic **propiedades**. La pantalla mostrada debe contener los campos especificados en el archivo TransmitHandler.xsd.
