---
title: Realización de pruebas unitarias | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40275d0b-b2ee-400c-9ef5-b9386ab0ae53
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36ede86266ea02b05249aa3edd655f3b10a27f3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007589"
---
# <a name="performing-unit-testing"></a>Realización de pruebas unitarias
Las pruebas unitarias se centran en el nivel de componente y es básicamente una prueba de correcto o incorrecto que comprueba si los componentes individuales de la solución de BizTalk se realizan según lo previsto. Tiene varias opciones para la solución de BizTalk de pruebas unitarias.  

## <a name="using-visual-studio"></a>Usar Visual Studio  
 Funcionalidad de pruebas unitarias está disponible con Visual Studio 2008 y versiones posteriores. Para obtener más información acerca de la funcionalidad de pruebas que está disponible con Visual Studio, consulte [probar la aplicación](http://go.microsoft.com/fwlink/?LinkId=159595) (http://go.microsoft.com/fwlink/?LinkId=159595).  

 BizTalk Server también proporciona un característica de pruebas unitarias para habilitar a los usuarios crear pruebas unitarias para los esquemas, asignaciones y canalizaciones. Para obtener más información sobre esta característica, consulte [Unit Testing con proyectos de BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=158270) (http://go.microsoft.com/fwlink/?LinkId=158270).  

> [!NOTE]  
>  Visual Studio es muy útil para los artefactos de BizTalk como orquestaciones, esquemas, canalizaciones y los componentes de canalización de pruebas unitarias. BizTalk Server proporciona las clases de prueba que puede usar con Visual Studio Team System para probar los artefactos de BizTalk.  

## <a name="using-non-microsoft-tools"></a>Uso de herramientas que no son de Microsoft  
 Otras dos herramientas utilizadas para las soluciones de BizTalk de pruebas unitarias son **BizUnit** y **NUnit**. **BizUnit** funciona perfectamente con Visual Studio Team System Test Edition. De forma similar, **NUnit** pruebas pueden modificarse fácilmente para que pueda ejecutar como-está en Visual Studio Team System Test Edition. Para obtener más información acerca de estas herramientas, consulte [herramientas para pruebas](~/technical-guides/tools-for-testing.md).  

> [!NOTE]  
>  El uso de **BizUnit** y **NUnit** no son compatibles con Microsoft, y Microsoft no ofrece ninguna garantía sobre la idoneidad de estos programas. El uso de estos programas queda bajo su propia responsabilidad.  

## <a name="using-the-biztalk-server-sdk"></a>Con el SDK de BizTalk Server  
 Puede realizar la unidad de las pruebas individuales de artefactos de BizTalk con las utilidades disponibles en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK. En la tabla siguiente proporciona un resumen de las utilidades de SDK que puede utilizarse para las pruebas unitarias:  


|    **Utilidad**     |                                                                                                                                                                                                                                                                   **Finalidad**                                                                                                                                                                                                                                                                   |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utilidad del remitente de AS2 |                                                                                                                                                                                              Le permite enviar un mensaje AS2 a un sitio Web en un único equipo. Esta utilidad simula el envío de un mensaje AS2 de un equipo diferente.                                                                                                                                                                                              |
|     DSDump.exe     |                                                                                  Permite volcar la estructura de esquemas de documento, que es una representación ligera en memoria de uno o varios esquemas XSD, con o sin anotaciones de archivo sin formato. Esta herramienta puede resultar útil al obtener errores del motor de análisis, por ejemplo, $Root$0$3$2 y cuando sea necesario descodificarlos. Los números detrás de $ quieren decir índices o registros de base 0 cuando aparecen en el esquema de documentos.                                                                                   |
|     FFAsm.exe      |                                                                                                                                                                        Ejecuta el componente de ensamblador de archivos sin formato, invocándolo directamente mediante la emulación de un componente de canalización que permite ver cómo serializa o ensambla documentos de XML de usuarios en un documento de archivo sin formato.                                                                                                                                                                        |
|     FFDasm.exe     |                                                                                                                                                                 Ejecuta el componente de desensamblador de archivo sin formato, invocándolo directamente mediante la emulación de un componente de canalización de recepción que permite ver cómo analiza o desensambla un documento de archivo sin formato de usuario en uno o varios documentos XML.                                                                                                                                                                  |
|    Pipeline.exe    | Se ejecuta un envío o recepción de la canalización; acepta uno o varios documentos de entrada y sus partes, esquemas XSD e información relacionada; y genera un documento de salida después de la canalización ejecuta. Pipeline.exe no tiene acceso a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos, por lo que canalizaciones que contienen componentes de ensamblador y desensamblador de BizTalk Framework que tienen acceso a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos durante la ejecución pueden no ser compatible. |
|     XMLAsm.exe     |                                                                                                                                                                    Ejecuta el componente de ensamblador XML, invocándolo directamente mediante la emulación de una canalización de envío que permite ver cómo serializa, ensambla o protegen con doble cifrado documentos XML de usuario en un documento XML de salida.                                                                                                                                                                    |
|    XMLDasm.exe     |                                                                                                                                                                Ejecuta el componente de desensamblador XML, invocándolo directamente mediante la emulación de una canalización de recepción que permite ver cómo analizar, desensamblar o desproteger un documento XML de usuario con doble cifrado en uno o varios documentos XML.                                                                                                                                                                |

 Para obtener más información acerca de las utilidades disponibles en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK, consulte [utilidades del SDK](http://go.microsoft.com/fwlink/?LinkId=154387) (<http://go.microsoft.com/fwlink/?LinkId=154387>).  

## <a name="see-also"></a>Vea también  
 [Herramientas para pruebas](~/technical-guides/tools-for-testing.md)