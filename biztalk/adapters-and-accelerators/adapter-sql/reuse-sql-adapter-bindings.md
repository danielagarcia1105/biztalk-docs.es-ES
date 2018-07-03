---
title: Volver a usar los enlaces del adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8bc8140f-1d40-492c-bce1-b85e992b3567
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6995f62b6dc94734b6e5dac01fad4284e6fcf7fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009989"
---
# <a name="reuse-sql-adapter-bindings"></a>Volver a usar los enlaces del adaptador de SQL
Un enlace crea una asignación entre un punto de conexión lógico (por ejemplo, un puerto de orquestación o un vínculo de rol) y un punto de conexión física (por ejemplo, un envío y puerto de recepción). Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk. Puede crear enlaces mediante la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="what-is-a-binding-file"></a>¿Qué es un archivo de enlace?  
 Un archivo de enlace es un archivo XML que contiene información de enlace para cada orquestación de BizTalk en el ámbito de un ensamblado de BizTalk, la aplicación o el grupo. Describe el archivo de enlace:  
  
- El host al que se enlaza cada orquestación.  
  
- El nivel de confianza del host.  
  
- La configuración para cada puerto de envío, puerto de recepción, ubicación de recepción y entidad que se ha configurado.  
  
  Puede generar archivos de enlace y, a continuación, aplicar los enlaces que contienen a un ensamblado, aplicación o grupo. Esto evita tener que configurar manualmente los enlaces en diferentes entornos de implementación y acelera la implementación de la aplicación.  
  
  No se genera automáticamente un archivo de enlace de un ensamblado, aplicación o el grupo de BizTalk. Sin embargo, puede generar un archivo de enlace mediante la exportación de enlaces. De forma similar, a continuación, puede importar el archivo de enlace a una aplicación o grupo. Esta sección proporciona instrucciones sobre cómo importar y exportar enlaces.  
  
  Para obtener más información acerca de los enlaces y los archivos de enlace, consulte [archivos de enlace e implementación de aplicaciones](../../core/binding-files-and-application-deployment.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupo Administradores u operadores de BizTalk. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), y [derechos mínimos de seguridad](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).
 
## <a name="export-bindings"></a>Exportar enlaces
En esta sección se describe cómo exportar enlaces para una aplicación de BizTalk en un archivo XML. A continuación, puede importar los enlaces del archivo XML en otra aplicación de BizTalk. Importar enlaces sobrescriben los enlaces existentes del mismo nombre en la aplicación. También puede agregar enlaces a una aplicación, con lo que no se sobrescriben los enlaces existentes. Los enlaces que se agregan no se aplican hasta que se importa la aplicación.  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Haga clic en la aplicación cuyos enlaces desee exportar, seleccione **exportar**y, a continuación, seleccione **enlaces**.  
  
4. En el **exportar enlaces** página **exportación a archivo**, escriba la ruta de acceso absoluta del archivo XML que se va a exportar los enlaces.  
  
    Por ejemplo, escriba `C:\Bindings\Application1Bindings.Binding1.xml`  
  
5. Confirme que **exportar todos los enlaces de la aplicación actual** está seleccionada.  
  
6. Para exportar toda la información de entidad para el grupo, seleccione el **información de entidad Global exportar** casilla de verificación.  
  
7. Seleccione **Aceptar**. Los enlaces se exportan a un archivo XML en la ubicación que especificó.  

## <a name="import-bindings"></a>Importar enlaces
Importar enlaces mediante la consola de administración de BizTalk Server.
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. Expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
3. Haga clic en la aplicación en la que desea importar los enlaces, seleccione **importar**y, a continuación, seleccione **enlaces**.  
  
4. Seleccione el archivo de enlace y, a continuación, seleccione **abierto**.  
  
Los artefactos del archivo de enlace se escriben en la aplicación. Se muestran en las carpetas correspondientes de la aplicación. Por ejemplo, los puertos de envío se importan como parte de la presentación de enlaces bajo el **puertos de envío** carpeta.  

## <a name="passwords-are-removed"></a>Las contraseñas se quitan  
Por motivos de seguridad, al exportar un archivo de enlace, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] quita las contraseñas para los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configurar las contraseñas en el cuadro de diálogo Propiedades de transporte de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] administración de la consola para el puerto de envío o ubicación de recepción. 

Para obtener información acerca de cómo especificar el nombre de usuario y contraseñas, consulte [configurar el inicio de sesión en las credenciales de SQL Server](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md).
  
## <a name="see-also"></a>Vea también  
[Bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)