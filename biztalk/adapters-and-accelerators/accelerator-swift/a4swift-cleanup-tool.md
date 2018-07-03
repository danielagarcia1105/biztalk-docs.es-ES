---
title: Herramienta de limpieza de A4SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- A4SWIFT Cleanup tool
ms.assetid: e694f824-6097-4d60-bc7b-b4f1a40acea0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db6e9f6f6ec25762abc4416bc18f0955055b7e70
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983621"
---
# <a name="a4swift-cleanup-tool"></a>Herramienta de limpieza de A4SWIFT
El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Liberador de espacio permite preparar un servidor que tenga Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] instalado en él para una instalación nueva de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]. La herramienta quita los artefactos de A4SWIFT como contratos, los departamentos de TI y directivas del motor de reglas de negocios (BRE) y anula la implementación de ensamblados. Ejecutar la herramienta le permite evitar la eliminación manual de numerosos artefactos de A4SWIFT y resuelve los problemas con los ensamblados de anular la implementación que se pueden hacer referencia desde otros ensamblados.  
  
 Al ejecutar la herramienta de limpieza, tiene la opción de dejar instalada en el equipo (predeterminado), o la desinstalación de A4SWIFT después de quitar los artefactos de A4SWIFT. Debe ejecutar la herramienta antes de desinstalar A4SWIFT.  
  
> [!CAUTION]
>  No utilice la herramienta de limpieza de A4SWIFT en un entorno de producción. La herramienta está diseñada para usarse en un entorno de desarrollo de servidor único, no en una implementación multiservidor.  
  
> [!NOTE]
>  De forma predeterminada, la herramienta de limpieza no funciona para cualquier otro idioma de inglés. Sin embargo, puede modificar el entorno para que funcione la herramienta de limpieza en un equipo localizado. Ejecutar la herramienta FormPublish con el parámetro t y la cadena localizada para la biblioteca de documentos de plantillas, por ejemplo, **t:VorLagen** en un entorno de alemán. A continuación, puede ejecutar la herramienta de limpieza en un entorno localizado.  
  
 El siguiente debe ser true ejecutar la herramienta de limpieza:  
  
- Debe ser miembro del [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] grupos de administradores.  
  
- [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] debe instalarse en el servidor en el que ejecutar la herramienta.  
  
- MrsrConfiguration.dll, cree y RuleEngineExtension.dll deben implementarse en el servidor en el que ejecutar la herramienta.  
  
## <a name="what-the-cleanup-tool-does"></a>Lo que hace la herramienta de limpieza  
 La herramienta de limpieza de A4SWIFT realiza las siguientes operaciones:  
  
- Ejecuciones **anular la implementación de BM** contra ForActivities.xml y MRSRBAM.xml  
  
- Quita los archivos FrrActivities_ConnectionStrings.xml y MRSRActivities_ConnectionStrings.xml, si existen  
  
- Quita A4SWIFT 2.1, si existe (si ha actualizado el servidor a [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], pero el programa de instalación ha dejado 2.1 A4SWIFT instalado) y elimina la carpeta 2.1 de A4SWIFT  
  
- Anula la implementación de todos los ensamblados de A4SWIFT  
  
- Elimina el grupo de administradores de A4SWIFT y el grupo de usuarios de A4SWIFT  
  
- Elimina la base de datos de A4SWIFT  
  
- Elimina el directorio virtual de A4SWIFT  
  
- Se ejecuta una desinstalación silenciosa completa de [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] y elimina el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] carpeta (si ha seleccionado)  
  
  Ya que quita los artefactos y anula la implementación de ensamblados, la herramienta de limpieza también hace lo siguiente:  
  
- Se inicia Internet Information Services (IIS) Administrador Service para poder ejecutar  
  
- Se detiene y, a continuación, reinicia los servicios MSSQLSERVER, SQLSERVERAGENT, BizTalk y Enterprise Single Sign-On  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a>Para ejecutar la herramienta de limpieza de A4SWIFT  
  
1. Antes de ejecutar la herramienta de limpieza de A4SWIFT, anular la implementación de cualquier proyecto que hace referencia a cualquiera de los ensamblados predeterminados de A4SWIFT.  
  
2. Abra un símbolo del sistema y vaya a \< *unidad*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools.  
  
3. Tipo **A4SWIFTCleanupTool.exe** y, a continuación, presione **ENTRAR**.  
  
   > [!NOTE]
   >  Cuando se ejecuta inicialmente A4SWIFTCleanupTool.exe, la herramienta mostrará una pantalla de ayuda y le pide que escriba un parámetro. La herramienta no se ejecutará hasta que se especifique el parámetro.  
  
4. Dependiendo de las acciones que desea que realice la herramienta, presione una de las claves siguientes y, a continuación, presione **ENTRAR**:  
  
   - **0** para ninguna acción realizada (valor predeterminado)  
  
   - **1** para quitar todos los recursos de A4SWIFT locales en el equipo, incluida la configuración del registro y de directorio virtual  
  
   - **2** para quitar todos los recursos compartidos de A4SWIFT en el grupo de BizTalk Server, incluidas las carpetas Sharepoint Web, las plantillas de mensaje FIN, las directivas del BRE y vocabularios, artefactos de BizTalk y la base de datos de A4SWIFT  
  
   - **3** para quitar todos los recursos locales y compartidos  
  
   - **4** para quitar todos los recursos locales y compartidos y desinstalar el [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] producto.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas](../../adapters-and-accelerators/accelerator-swift/tools.md)