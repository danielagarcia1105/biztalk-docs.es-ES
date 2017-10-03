---
title: Conectarse a Oracle E-Business Suite en Visual Studio mediante el Asistente para agregar metadatos de adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4fadc722-0098-457e-a2e2-3e9cc96eab5e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5950b9ea6a0f5fc9856720202059cf1fd058a251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-add-adapter-metadata-wizard"></a>Conectarse a Oracle E-Business Suite en Visual Studio mediante el Asistente para agregar metadatos de adaptador
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] también se expone como un adaptador de BizTalk y, por lo tanto, puede usar el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar el esquema para las operaciones que desea realizar en Oracle E-Business Suite mediante el adaptador.  
  
## <a name="connecting-to-oracle-e-business-suite-using-the-add-adapter-metadata-wizard"></a>Conectarse a Oracle E-Business Suite utilizando los metadatos de Asistente para agregar adaptador  
 Realice los pasos siguientes para conectarse a Oracle E-Business Suite mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
#### <a name="to-connect-to-oracle-e-business-suite"></a>Para conectarse a Oracle E-Business Suite  
  
1.  Para conectarse mediante la [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] en una solución de BizTalk:  
  
    1.  Cree un proyecto de BizTalk mediante Visual Studio.  
  
    2.  Haga clic en el proyecto en el Explorador de soluciones, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
    3.  En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Categorías**|Haga clic en **agregar adaptador**.|  
        |**Plantillas**|Haga clic en **agregar metadatos de adaptador**.|  
  
    4.  Haga clic en **Agregar**. Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].  
  
    5.  En el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], seleccione **WCF-OracleEBS**. Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.  
  
        > [!IMPORTANT]
        >  Si ya tiene un puerto de WCF-OracleEBS configurado en BizTalk, seleccione el puerto de la **puerto** lista.  
  
    6.  Haga clic en **Siguiente**.  
  
2.  Desde el **selecciona un enlace** lista desplegable, seleccione **oracleEBSBinding** y haga clic en **configurar**.  
  
3.  En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  
  
    |||  
    |-|-|  
    |Use|Para|  
    |**Para conectarse con credenciales de base de datos de Oracle**|Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.|  
    |**Para conectarse con credenciales de Oracle E-Business Suite**|Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace.|  
    |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**|Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.|  
    |**Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"**|Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlace de propiedad en blanco.|  
  
4.  Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)).  
  
    > [!NOTE]
    >  Si los parámetros de conexión contienen caracteres reservados, debe especificarlos tal-está en la **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con caracteres de escape adecuados.  
  
5.  Haga clic en el **propiedades de enlace** ficha y, a continuación, especifique valores para las propiedades de enlace, si existe, requeridos por las operaciones de destino. Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
    > [!NOTE]
    >  Si va a generar los metadatos que utilizan [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] y ha seleccionado un puerto de envío WCF-OracleEBS existente, no es necesario especificar las propiedades de enlace. Las propiedades de enlace se toman de la configuración del puerto de envío. Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si los hubiera. En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos. Sin embargo, en tiempo de ejecución se pueden aplicables los valores especificados para propiedades de enlace en la configuración del puerto de envío.  
  
6.  Haga clic en **Aceptar**.  
  
7.  Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  
  
     La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión.  
  
     ![Utilizar el cuadro de diálogo de servicio de adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  
  
     La [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] muestra los distintos nodos que contiene varias operaciones que se pueden realizar en la base de datos de Oracle y Oracle E-Business Suite. Para obtener más información sobre cómo se clasifica por categorías los metadatos en los distintos nodos, consulte [conectarse a Oracle E-Business Suite en Visual Studio mediante el Asistente para agregar metadatos de adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [Conectarse a Oracle E-Business Suite mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)