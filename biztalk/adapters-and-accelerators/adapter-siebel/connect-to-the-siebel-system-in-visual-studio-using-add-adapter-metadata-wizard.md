---
title: Conectarse al sistema Siebel en Visual Studio mediante metadatos Asistente para agregar adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0a82fcc-b3ac-4936-9210-03c99d3741d7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 700c2ad92cd03b50808f6a785b34b4d745482acb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983493"
---
# <a name="connect-to-the-siebel-system-in-visual-studio-using-add-adapter-metadata-wizard"></a>Conectarse al sistema Siebel en Visual Studio mediante metadatos Asistente para agregar adaptador
El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] también se expone como un adaptador de BizTalk y por lo tanto, puede usar el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para las operaciones que desea realizar en el sistema de Siebel mediante el adaptador.  

## <a name="connecting-to-a-siebel-system-using-add-adapter-metadata-wizard"></a>Conectarse a un sistema de Siebel mediante metadatos Asistente para agregar adaptador  
 Realice los pasos siguientes para conectarse a un sistema de Siebel mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

#### <a name="to-connect-to-a-siebel-system"></a>Para conectarse a un sistema de Siebel  

1. Para conectarse mediante la [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] en una solución de BizTalk:  

   1. Cree un proyecto de BizTalk con [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  

   2. Haga clic en el proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  

   3. En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  


      |    Use    |             Para             |
      |----------------|------------------------------------|
      | **Categorías** | Haga clic en **Consume Adapter Service**. |
      | **Templates** (Plantillas [C++])  | Haga clic en **Consume Adapter Service**. |


   4. Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  

   5. En el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], seleccione Siebel de WCF. Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.  

      > [!IMPORTANT]
      >  Si ya tiene un **WCF-Siebel** BizTalk configurada en el puerto, seleccione el puerto de la **puerto** lista.  

   6. Haga clic en **Siguiente**.  

2. Desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y, a continuación, haga clic en **configurar**.  

3. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario**.  

4. Especifique el nombre de usuario y contraseña para conectarse al sistema Siebel.  

5. Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [crear el URI de conexión del sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  

   > [!NOTE]
   >  Si los parámetros de conexión contienen caracteres reservados, deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  

6. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, requeridos por las operaciones que desea dirigirse. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).  

   > [!NOTE]
   >  Si va a generar los metadatos mediante [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] y ha seleccionado un puerto de envío WCF-Siebel existente, no es necesario especificar las propiedades de enlace. Se seleccionan las propiedades de enlace de la configuración de puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.  

7. Haga clic en **Aceptar**.  

8. Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  

    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión.  

    ![Consumo de servicio de adaptador de cuadro de diálogo conectado](../../adapters-and-accelerators/adapter-siebel/media/siebel-adpt-lesson1-step3-01-connected.gif "SIEBEL-ADPT-Lesson1-Step3-01-connected")  

    La [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] muestra los diferentes nodos que contiene las distintas operaciones que se pueden realizar en el sistema Siebel. Por ejemplo, el **objetos de negocios** nodo contiene todos los objetos de negocios y los componentes empresariales que se pueden invocar en el sistema Siebel. De forma similar, el **servicios empresariales** nodo contiene todos los servicios de negocios en el sistema de Siebel es conectado. Para obtener más información acerca de estos nodos, consulte [identificadores de nodo de metadatos](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md).