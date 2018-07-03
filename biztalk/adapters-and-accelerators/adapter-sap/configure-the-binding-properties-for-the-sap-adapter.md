---
title: Configurar las propiedades de enlace para el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef599f91675d4604d9e9f56aafdef3677d2583a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001973"
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a>Configurar las propiedades de enlace para el adaptador de SAP
La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento. Esta sección proporciona información acerca de cómo establecer las propiedades de enlace de Visual Studio (tiempo de diseño) y de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración (tiempo de ejecución). En tiempo de diseño, debe especificar las propiedades de enlace para generar esquemas para operaciones específicas. En tiempo de ejecución, debe especificar las propiedades de enlace como parte de envío o puerto de recepción para enviar o recibir mensajes desde el sistema SAP.  

 Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  

## <a name="enter-binding-properties-at-design-time"></a>Escribir propiedades de enlace en tiempo de diseño  
 Para el tiempo de diseño, puede especificar las propiedades de enlace mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a>Escribir propiedades de enlace mediante el complemento Consume Adapter Service  

1.  Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **Consume Adapter Service**.|  

3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  

4.  En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sapBinding**y haga clic en **configurar** .  

5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique las propiedades de enlace diferente.  

6.  Haga clic en **Aceptar**.  

### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a>Escribir propiedades de enlace mediante el Asistente para agregar metadatos de adaptador  

1. Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


   |    Use    |           Para            |
   |----------------|---------------------------------|
   | **Categorías** |     Haga clic en **agregar adaptador**.      |
   | **Templates** (Plantillas [C++])  | Haga clic en **agregar metadatos de adaptador**. |


3. Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

4. En el Asistente para agregar adaptador, seleccione **SAP de WCF**. Seleccione el equipo donde está instalado BizTalk Server y el nombre de la base de datos de BizTalk.  

   > [!IMPORTANT]
   >  Si ya tiene un puerto de SAP de WCF configurado en BizTalk, seleccione el puerto desde el **puerto** lista.  

5. Haga clic en **Siguiente**.  

6. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sapBinding**y haga clic en **configurar** .  

7. Haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que deben especificarse antes de generar el esquema. Por ejemplo, debe especificar un valor para el **GenerateFlatFileCompatibleIDoc** propiedad antes de generar el esquema para recibir IDOC desde un sistema SAP. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  

   > [!NOTE]
   >  Si ha seleccionado un puerto de envío WCF-SAP existente, no necesita especificar las propiedades de enlace. Se seleccionan las propiedades de enlace de la configuración de puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.  

8. Haga clic en **Aceptar**.  

## <a name="enter-binding-properties-at-run-time"></a>Escribir propiedades de enlace en tiempo de ejecución  
 Para el tiempo de ejecución, puede especificar las propiedades de enlace como parte del puerto de WCF-Custom o configuración de SAP de WCF en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

### <a name="enter-binding-properties-for-the-wcf-custom-port"></a>Especifique las propiedades de enlace para el puerto de WCF-Custom  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

3. En el **propiedades de puerto** cuadro de diálogo desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.  

5. Desde el **BindingType** lista desplegable, seleccione **sapBinding**.  

6. En el **configuración** cuadro, especifique los valores de las propiedades de enlace diferente y, a continuación, haga clic en **Aceptar**.  

### <a name="enter-binging-properties-for-the-wcf-sap-port"></a>Especifique las propiedades de enlace para el puerto de SAP de WCF  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).  

3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

5. En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.  

   > [!NOTE]
   >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, operaciones relacionadas con entrada de enlace de propiedades no están disponibles al configurar un puerto de envío debido a operaciones de entrada requieren una configuración de puerto de recepción.  

6. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)