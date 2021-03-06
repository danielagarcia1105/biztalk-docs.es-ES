---
title: Configurar las propiedades de enlace del adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2edbd90-039a-48b4-a6fc-d825b4957207
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 013d9b2b5da755101b53420f2b29fb639851d230
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010069"
---
# <a name="configure-the-binding-properties-for-the-sql-adapter"></a>Configurar las propiedades de enlace del adaptador de SQL
La [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento. Esta sección proporciona información acerca de cómo establecer las propiedades de enlace de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar las propiedades de enlace para generar esquemas para operaciones específicas. Desde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe especificar las propiedades de enlace como parte de envío o puerto de recepción para enviar o recibir mensajes de SQL Server.  

 Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  

## <a name="enter-the-binding-properties-in-visual-studio"></a>Escriba las propiedades de enlace en Visual Studio  
 Desde [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], puede especificar las propiedades de enlace mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

### <a name="using-consume-adapter-service-add-in"></a>Utilizando consumir el adaptador de complemento de servicio  

1.  Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.  

2.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  

    |Use|Para|  
    |--------------|----------------|  
    |**Categorías**|Haga clic en **Consume Adapter Service**.|  
    |**Templates** (Plantillas [C++])|Haga clic en **Consume Adapter Service**.|  

3.  Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.  

4.  En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  

5.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique las propiedades de enlace diferente.  

6.  Haga clic en **Aceptar**.  

### <a name="using-add-adapter-metadata-wizard"></a>Uso de metadatos de Asistente para agregar adaptador  

1. Haga clic en el proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

2. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


   |    Use    |           Para            |
   |----------------|---------------------------------|
   | **Categorías** |     Haga clic en **agregar adaptador**.      |
   | **Templates** (Plantillas [C++])  | Haga clic en **agregar metadatos de adaptador**. |


3. Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

4. En el Asistente para agregar adaptador, seleccione **WCF-SQL**. Seleccione el equipo donde está instalado BizTalk Server y el nombre de la base de datos de BizTalk.  

   > [!IMPORTANT]
   >  Si ya tiene un puerto de WCF-SQL configurado en BizTalk, seleccione el puerto desde el **puerto** lista.  

5. Haga clic en **Siguiente**.  

6. En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sqlBinding**y, a continuación, haga clic en **configurar**.  

7. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, requeridos por las operaciones que desea dirigirse. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  

   > [!NOTE]
   >  Si ha seleccionado un puerto de envío WCF-SQL existente, no necesita especificar las propiedades de enlace. Se seleccionan las propiedades de enlace de la configuración de puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.  

8. Haga clic en **Aceptar**.  

## <a name="enter-binding-properties-from-the-biztalk-server-administration-console"></a>Escribir propiedades de enlace desde la consola de administración de BizTalk Server  
 Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede especificar las propiedades de enlace como parte de la configuración del puerto WCF-Custom o WCF-SQL.  

### <a name="enter-binding-properties-for-wcf-custom-port"></a>Especifique las propiedades de enlace de puerto personalizado de WCF  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

3. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

4. En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.  

5. Desde el **BindingType** lista, seleccione **sqlBinding**.  

6. En el **configuración** cuadro, especifique los valores de las propiedades de enlace diferente y, a continuación, haga clic en **Aceptar**.  

### <a name="enter-binding-properties-for-the-wcf-sql-port"></a>Especifique las propiedades de enlace para el puerto de WCF-SQL  

1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

2. Agregar el adaptador de WCF-SQL para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Para obtener instrucciones, consulte [agregación del adaptador de SQL a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).  

3. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**. En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.  

4. En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-SQL que agregó anteriormente y, a continuación, haga clic en **configurar**.  

   > [!NOTE]
   >  Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.  

5. En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.  

   > [!NOTE]
   >  Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción. Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.  

6. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)