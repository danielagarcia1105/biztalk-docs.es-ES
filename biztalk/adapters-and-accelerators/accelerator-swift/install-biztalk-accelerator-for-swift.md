---
title: Instalar el Acelerador de BizTalk para SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- documentation
ms.assetid: 8d492248-fde6-4fd8-be6b-e86ac7d0808b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e28d5dac74bdbceb0fe4938810779d6ccb5c52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211628"
---
# <a name="install-biztalk-accelerator-for-swift"></a>Instalar el Acelerador de BizTalk para SWIFT
Instalar [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)] en BizTalk Server. 

\<!---Texto anterior
-   [Guía de instalación para el Acelerador de BizTalk para SWIFT](http://go.microsoft.com/fwlink/?LinkId=198120)    
-   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Archivo Léame, ubicado en el Acelerador de BizTalk para SWIFT \Documentation carpeta \Program.  
-->

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y de software

Los requisitos mínimos de hardware y software son los mismos que [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].

|  |Requisitos de BizTalk  |Requisitos de SQL y el sistema operativo |  
|---------|---------|--------- | 
| [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [Hardware and Software Requirements for BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016) | **Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx) |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [Requisitos de hardware y Software para BizTalk Server 2013 y 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) |**Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)  |

> [!TIP] 
> Los requisitos de hardware enumerados son los mínimos. Cada entorno es diferente y es muy probable que el suyo tenga más requisitos. Consulte [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx) (Recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución de BizTalk Server). 

## <a name="install-swift"></a>Instalar SWIFT

### <a name="before-you-begin"></a>Antes de empezar

* Inicie sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server. 
* En la descarga de BizTalk Server, el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] el programa de instalación está en la `\BizTalk Accelerators` carpeta.
* BizTalk Server debe estar instalado y debe estar ejecutando SQL Server.
* Una instalación silenciosa es compatible, pero no se recomienda debido a la complejidad de los pasos de configuración adicionales que son necesarios.
* El programa de instalación de A4SWIFT siempre se ejecuta con la `/InstallPlatform` argumento. Como resultado, el programa de instalación instala siempre msvcr71.dll, mfc71u.dll, msvcp71.dll y atl71.dll, que son necesarios para Visual Studio. El programa de instalación instala estos archivos DLL en el `%WINDIR%\System32` carpeta, si los archivos DLL instalados previamente o no.

### <a name="default-installation"></a>Instalación predeterminada

1. Ejecute el [!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe** como administrador.
2. Seleccione **Instalar**.
3. Escriba el **Nombre de usuario**, la **Organización** y la clave de producto. Seleccione **Siguiente**.
4. Lea el contrato de licencia y, a continuación, seleccione **Accept**.
5. Seleccione **completar**y, a continuación, seleccione **siguiente**.
6. Revise el **resumen** página. Para realizar cambios, seleccione **volver**.

    Para habilitar el inicio de sesión automático después de reiniciar el sistema, seleccione **Establecer** y especifique la cuenta de inicio de sesión. Esto solo está habilitada durante la instalación. Cuando finalice la instalación, esta configuración se deshabilita.

    Seleccione **Instalar**.
 
7. Seleccione **finalizar** cuando haya terminado. Se genera un archivo de registro de instalación en una carpeta temporal, similar a: `C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`.

> [!NOTE] 
> Si **ejecutar el Asistente para configuración** está seleccionado en la página Instalación completada, el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Asistente de configuración se ejecuta automáticamente al hacer clic en **finalizar**. 


### <a name="custom-installation"></a>Instalación personalizada

1. Ejecute el [!INCLUDE[btaA4SWIFTNoVersion_md](../../includes/btaa4swiftnoversion-md.md)] **setup.exe** como administrador.
2. Seleccione **Instalar**.
3. Escriba el **Nombre de usuario**, la **Organización** y la clave de producto. Seleccione **Siguiente**.
4. Lea el contrato de licencia y, a continuación, seleccione **Accept**.
5. Seleccione **personalizado**y, a continuación, seleccione **siguiente**.
6. Seleccione los componentes y, a continuación, seleccione **siguiente**:

    | Seleccione | Para |
    | --- | --- |
    | Componentes de A4Swift | Necesario para el proceso (resolución de esquemas, análisis, validación) de los mensajes de SWIFT con BizTalk Server |
    | Conciliación y reparación de mensajes | Instalar las canalizaciones, orquestaciones y esquemas en tiempo de ejecución. Crea la base de datos de A4SWIFT en SQL Server para la mensajería, reparación y conciliación. |
    | Componentes Web de reparación de mensajes y nuevo envío | Instala el componente de reparación de mensajes y nuevo envío que crean servicios web para la validación, el certificado de seguridad, el historial y búsqueda BIC. |
    | Kit de desarrollo de software (SDK) | Incluye proyectos de inicio, código y kits de herramientas de código fuente de ejemplo para Visual Studio. | 
    | Utilidad de implementación de BRE | Utilidad para implementar las directivas del motor de reglas de negocios (BRE) asociadas a los tipos de mensaje SWIFT que ya estén implementados. |
    | Tutorial | Iincludes instrucciones y ejemplos para desarrollar una solución sencilla en BizTalk Server. |
    | Herramientas | Incluye herramientas para el desarrollo de A4SWIFT. |
    | Source | Instala muestra el código fuente para el desarrollo de A4SWIFT. |
    
6. Revise el **resumen** página. Para realizar cambios, seleccione **volver**.

    Seleccione **Instalar**.
 
7. Seleccione **finalizar** cuando haya terminado. Se genera un archivo de registro de instalación en una carpeta temporal, similar a: `C:\Users\username\AppData\Local\Setup(111016 xxxxxx).log`.

> [!NOTE]
> Si **ejecutar el Asistente para configuración** está seleccionado en la página Instalación completada, el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] Asistente de configuración se ejecuta automáticamente al hacer clic en **finalizar**. 

## <a name="next-steps"></a>Pasos siguientes
[Configurar el Acelerador de BizTalk para SWIFT](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)