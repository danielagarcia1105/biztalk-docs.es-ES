---
title: Reutilizar los enlaces del adaptador con Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb4dd90d-7958-4d62-bc7b-d6be16288dbc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25aec8346a4252902e37a778384ae603852a11be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reuse-adapter-bindings-with-oracle-e-business-suite"></a>Reutilizar los enlaces del adaptador con Oracle E-Business Suite
Un enlace crea una asignación entre un extremo lógico (por ejemplo, un puerto de orquestación o un vínculo de función) y un extremo físico (por ejemplo, un envío y puerto de recepción). Esto permite la comunicación entre distintos componentes de un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución empresarial. Puede crear enlaces mediante el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="what-is-a-binding-file"></a>¿Qué es un archivo de enlace?  
 Un archivo de enlace es un archivo XML que contiene información de enlace para cada orquestación de BizTalk en el ámbito de un ensamblado de BizTalk, la aplicación o el grupo. Describe el archivo de enlace:  
  
-   El host al que se enlaza cada orquestación.  
  
-   El nivel de confianza del host.  
  
-   La configuración para cada puerto de envío, puerto de recepción, ubicación de recepción y entidad a la que se ha configurado.  
  
 Puede generar archivos de enlace y, a continuación, aplicar los enlaces que contienen a un ensamblado, la aplicación o el grupo. Esto evita tener que configurar manualmente los enlaces en diferentes entornos de implementación y acelera la implementación de la aplicación.  
  
 Un archivo de enlace no se genera automáticamente para un ensamblado, aplicación o el grupo de BizTalk. Sin embargo, puede generar un archivo de enlace mediante la exportación de enlaces. Del mismo modo, a continuación, puede importar el archivo de enlace en una aplicación o un grupo. Esta sección proporciona instrucciones sobre cómo importar y exportar enlaces.  
  
 Para obtener más información sobre los enlaces y los archivos de enlace, vea [archivos de enlace y la implementación de aplicaciones](../../core/binding-files-and-application-deployment.md).

 > [!NOTE]
 >  Un archivo de enlace no se genera automáticamente para un ensamblado, aplicación o el grupo de BizTalk. Aunque puede generar un archivo de enlace mediante la exportación de enlaces. A continuación, puede importar el archivo de enlace en una aplicación o un grupo.  
 
## <a name="prerequisites"></a>Requisitos previos    
Inicie sesión en i-ésimo una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).

## <a name="export-bindings"></a>Exportar enlaces

En esta sección se describe cómo exportar enlaces de una aplicación de BizTalk en un archivo XML. A continuación, puede importar los enlaces desde el archivo XML en otra aplicación de BizTalk. Importar enlaces sobrescriben los enlaces existentes del mismo nombre en la aplicación. También puede agregar enlaces a una aplicación, con lo que no se sobrescriben los enlaces existentes. Los enlaces que se agregan no se aplican hasta que se importa la aplicación.  

1.  Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Haga clic en la aplicación cuyos enlaces desee exportar, seleccione **exportar**y, a continuación, seleccione **enlaces**.  
  
4.  En el **exportar enlaces** página **exportación a archivo**, escriba la ruta de acceso absoluta del archivo XML que se va a exportar los enlaces.  
  
     Por ejemplo, escriba`C:\Bindings\Application1Bindings.Binding1.xml`  
  
5.  Confirme que **exportar todos los enlaces de la aplicación actual** está seleccionada.  
  
6.  Para exportar toda la información de entidad para el grupo, seleccione el **información de entidad Global exportar** casilla de verificación.  
  
7.  Seleccione **Aceptar**. Los enlaces se exportan a un archivo XML en la ubicación que especificó.  

## <a name="import-bindings"></a>Importar enlaces

Importar enlaces mediante la consola de administración de BizTalk Server.
  
1.  Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3.  Haga clic en la aplicación en la que desea importar los enlaces, seleccione **importar**y, a continuación, seleccione **enlaces**.  
  
4.  Seleccione el archivo de enlace y, a continuación, seleccione **abiertos**.  
  
Los artefactos del archivo de enlace se escriben en la aplicación. Se muestran en las carpetas correspondientes de la aplicación. Por ejemplo, los puertos de envío se importan como parte de la pantalla de enlaces bajo el **puertos de envío** carpeta.  
  
## <a name="passwords-are-removed"></a>Se eliminan las contraseñas  
Por motivos de seguridad, cuando se exporta un archivo de enlace [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] administración de la consola del puerto de envío o ubicación de recepción. 

Para obtener información acerca de cómo especificar el nombre de usuario y contraseñas, consulte [configurar las credenciales de inicio de sesión para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)