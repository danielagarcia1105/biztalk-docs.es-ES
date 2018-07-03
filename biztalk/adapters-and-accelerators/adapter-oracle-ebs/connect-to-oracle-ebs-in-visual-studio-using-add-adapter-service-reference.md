---
title: Conectarse a Oracle E-Business Suite en Visual Studio mediante el complemento Add Adapter Service Reference | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7fe4d1b7-8201-4816-ae90-020520f29714
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f5ef971b717c721aae9f6f753daaf6fe6eeb30d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976757"
---
# <a name="connect-to-oracle-e-business-suite-in-visual-studio-using-add-adapter-service-reference-plug-in"></a>Conectarse a Oracle E-Business Suite en Visual Studio mediante el complemento Add Adapter Service Reference
Para conectarse a Oracle E-Business Suite mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] en una solución de programación. NET, se debe utilizar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Este tema proporciona instrucciones sobre cómo usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

## <a name="connecting-to-oracle-e-business-suite-using-the-add-adapter-service-reference-plug-in"></a>Conectarse a Oracle E-Business Suite utilizando el Add Adapter Service Reference complemento  
 Realice los pasos siguientes para conectarse a Oracle E-Business Suite mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

#### <a name="to-connect-to-oracle-e-business-suite"></a>Para conectarse a Oracle E-Business Suite  

1. Para conectarse mediante la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] en una solución de programación:  

   1. Crear un proyecto mediante Visual Studio.  

   2. Haga clic en el proyecto en el Explorador de soluciones y, a continuación, haga clic en **Add Adapter Service Reference**. Se abrirá [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

2. Desde el **selecciona un enlace** lista desplegable, seleccione **oracleEBSBinding** y haga clic en **configurar**.  

3. En el **configurar el adaptador** cuadro de diálogo, haga clic en el **seguridad** ficha y desde el **tipo de credencial de cliente** cuadro de lista desplegable, seleccione **denombredeusuario** y especifique el nombre de usuario y contraseña para conectarse a Oracle E-Business Suite.  


   |                                                                                           |                                                                                                                                                                                                                                                                                                         |
   |-------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                         Use                                          |                                                                                                                                               Para                                                                                                                                                |
   |                     **Para conectarse con credenciales de base de datos de Oracle**                      |                                                                          Especifique el **ClientCredentialType** enlazar la propiedad a **base de datos** y especifique las credenciales de la base de datos para **nombre de usuario** y **contraseña**cuadros de texto.                                                                          |
   |                 **Para conectarse con credenciales de Oracle E-Business Suite**                  | Especifique el **ClientCredentialType** enlazar la propiedad a **EBusiness** y especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña**  cuadros de texto. En este caso, también debe especificar las credenciales de la base de datos de Oracle para **OracleUserName** y **OraclePassword** propiedades de enlace. |
   | **Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "Base de datos"**  |                                                                                                         Especifique un "/" para el **nombre de usuario** cuadro de texto y dejar el **contraseña** cuadro de texto en blanco.                                                                                                         |
   | **Para conectarse mediante la autenticación de Windows si ClientCredentialType se establece en "EBusiness"** |                                       Especifique las credenciales de Oracle E-Business Suite para **nombre de usuario** y **contraseña** cuadros de texto. También debe especificar una "/" para el **OracleUserName** enlace de propiedad y deje el **OraclePassword** enlaza la propiedad en blanco.                                       |


4. Haga clic en el **propiedades de URI** pestaña y especificar valores para los parámetros de conexión. Para obtener más información sobre el URI de conexión para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).  

   > [!NOTE]
   >  Si los parámetros de conexión contienen caracteres reservados, deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Sin embargo, si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  

5. Haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique valores para las propiedades de enlace, si alguno, requeridos por las operaciones que desea dirigirse. Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  

6. Haga clic en **Aceptar**.  

7. Haga clic en **Conectar**. Una vez establecida la conexión, se muestra el estado de conexión como **conectado**.  

    La siguiente ilustración muestra el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] inmediatamente después de establecer la conexión. La interfaz gráfica de usuario es el mismo para el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

    ![Usar el cuadro de diálogo de servicio de adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/media/6a2b21ed-0fd2-4874-a6a6-e59a467533f8.gif "6a2b21ed-0fd2-4874-a6a6-e59a467533f8")  

    La [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] muestra los diferentes nodos que contiene las distintas operaciones que se pueden realizar en la base de datos de Oracle y Oracle E-Business Suite. Para obtener más información sobre cómo se clasifica por categorías los metadatos en los distintos nodos, consulte [conectarse a Oracle E-Business Suite en Visual Studio mediante el Asistente para agregar metadatos de adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md).  

## <a name="see-also"></a>Vea también  
 [Conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)   
 [Conectarse a Oracle E-Business Suite mediante la autenticación de Windows](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)