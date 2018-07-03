---
title: Configurar las propiedades de enlace para la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at run time
- binding properties, specifying at design time
ms.assetid: c59a1b5c-b52b-4161-82de-c4d89bfce5c7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96922feab7c343893bfaa04ccbccd7c7e2f6a743
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981085"
---
# <a name="configure-the-binding-properties-for-oracle-database"></a>Configurar las propiedades de enlace para la base de datos de Oracle
La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento. Esta sección proporciona información acerca de cómo establecer las propiedades de enlace desde Visual Studio y desde la consola de administración de BizTalk Server. Desde Visual Studio, debe especificar las propiedades de enlace al generar el esquema para operaciones específicas. Desde BizTalk Server, debe especificar las propiedades de enlace como parte de envío o puerto de recepción para enviar o recibir mensajes desde la base de datos de Oracle.  

 Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  

## <a name="specifying-binding-properties-from-visual-studio"></a>Especificar propiedades de enlace desde Visual Studio  
 Desde Visual Studio, debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a>Para especificar las propiedades de enlace mediante el complemento Consume Adapter Service  

1.  Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.  

2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **Consume Adapter Service**.|  

3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  

4.  En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **oracleDBBinding**y haga clic en **configurar**.  

5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y especificar las propiedades de enlace diferente.  

6.  Haga clic en **Aceptar**.  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a>Para especificar las propiedades de enlace mediante el Asistente para agregar metadatos de adaptador  

1. Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.  

2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


   |    Use    |           Para            |
   |----------------|---------------------------------|
   | **Categorías** |     Haga clic en **agregar adaptador**.      |
   | **Templates** (Plantillas [C++])  | Haga clic en **agregar metadatos de adaptador**. |


3. Haga clic en **Agregar**. Se abre el Asistente para agregar metadatos de adaptador.  

4. En el Asistente para agregar metadatos de adaptador, seleccione **WCF-OracleDB**. Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.  

   > [!IMPORTANT]
   >  Si ya tiene un puerto de WCF-OracleDB configurado en BizTalk, seleccione el puerto desde el **puerto** lista.  

5. Haga clic en **Siguiente**.  

6. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **oracleDBBinding**y haga clic en **configurar**.  

7. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que son necesarios antes de generar el esquema. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).  

   > [!NOTE]
   >  Si ha seleccionado un puerto de envío WCF-OracleDB existente, no necesita especificar las propiedades de enlace. Se seleccionan las propiedades de enlace de la configuración de puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe. En tal caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.  

8. Haga clic en **Aceptar**.  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a>Especificar propiedades de enlace desde la consola de administración de BizTalk Server  
 Desde la consola de administración de BizTalk Server, debe especificar las propiedades de enlace como parte de la configuración del puerto WCF-Custom o WCF-OracleDB.  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a>Para especificar las propiedades de enlace para el puerto de WCF-Custom  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.  

5. Desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.  

6. En el **configuración** , especifique los valores de las propiedades de enlace diferente y haga clic en **Aceptar**.  

#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a>Para especificar las propiedades de enlace para el puerto de WCF-OracleDB  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Agregar el adaptador de WCF-OracleDB a la consola de administración de BizTalk Server. Para obtener instrucciones, consulte [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).  

3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-OracleDB que agregó anteriormente y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

5. En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.  

   > [!NOTE]
   >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.  

## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)