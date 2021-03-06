---
title: Comprobar una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 265afd62-3c1d-4b9a-9f51-176b9b079241
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ad35dd513375f8221ed909fd7f353fc5e6673c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983941"
---
# <a name="testing-a-map"></a>Comprobar una asignación
Puede comprobar una asignación de un proyecto EDI en tiempo de diseño. Para ello, se usan las extensiones de la herramienta XML para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. En este tema se describe cómo configurar y usar el **comprobar asignación** característica de la extensión de la herramienta de XML.  
  
 Una asignación se puede probar al especificar un documento de origen y una carpeta en la que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] guardará una instancia generada (con datos ficticios). Debe establecer los delimitadores que el servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará para procesar el documento de origen y generar el documento de destino en función de los esquemas EDI. Esto es cierto para todos los valores de la **comprobar asignación** propiedad en páginas de propiedades de la asignación de entrada: **generar instancia**, **XML**, o **nativo**. Es true para **generar instancia** porque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe saber qué delimitadores usar para generar la instancia. Es true para **XML** o **nativo** porque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe saber cómo interpretar el archivo sin formato nativo o el archivo XML. También debe establecer los delimitadores que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará al generar el archivo de salida.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-test-a-map"></a>Para comprobar una asignación  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], agregue la asignación que desea comprobar a un proyecto, así como los esquemas de origen y destino para esa asignación en el proyecto.  
  
   > [!NOTE]
   >  No tiene que generar el proyecto para comprobar la asignación.  
  
2. Haga clic en el mapa y haga clic en **propiedades**.  
  
3. En el **propiedades** ventana, establezca **validar entrada de comprobar asignación** a **True** si desea validar el archivo de entrada con respecto al esquema de origen. Establecer **validar salida de comprobar asignación** a **True** si desea validar el archivo de salida con respecto al esquema de destino.  
  
   > [!NOTE]
   >  Si prueba una asignación con el **entrada de comprobar asignación** propiedad establecida en **nativo** y **validar entrada de comprobar asignación** y **validar salida de comprobar asignación** propiedades establecidas en **False**, todavía se realizará la validación. Esto ocurre porque el archivo de entrada de formato nativo se convertirá a formato XML, y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] validará el XML con respecto al esquema. Si hay problemas de validación en la instancia de entrada, el mecanismo de validación registrará errores, aunque el **validar entrada de comprobar asignación** y **validar salida de comprobar asignación** propiedades se establecen en **False**.  
  
4. Establecer **entrada de comprobar asignación** a **nativo** para un archivo de entrada que tiene una extensión de EDI. Establézcalo en **XML** si tiene una extensión .xml. Establecer **entrada de comprobar asignación** a **generar instancia** tener [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generar una instancia de entrada, no tener que designar una instancia de entrada manualmente.  
  
5. Establecer **salida de comprobar asignación** a **nativo** para un archivo de salida que tiene una extensión de EDI. Establézcalo en **XML** si tiene una extensión .xml.  
  
6. Para **instancia de entrada de comprobar asignación**, vaya a la instancia de entrada que desea que se usará para comprobar la asignación, seleccionarlo y, a continuación, **abierto**. Si desea dejar esta propiedad en blanco, establezca **entrada de comprobar asignación** a **generar instancia**.  
  
   > [!NOTE]
   >  Tiene que designar una instancia de entrada para **instancia de entrada de comprobar asignación** o establecer **entrada de comprobar asignación** a **generar instancia**. De no ser así, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará un error.  
  
7. Para **instancia de salida de comprobar asignación**, vaya a la ubicación que desee guardar la instancia de salida, escriba un nombre para la instancia de salida y, a continuación, haga clic en **guardar**.  
  
   > [!NOTE]
   >  Si no designa una instancia de salida, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creará un archivo de salida, lo colocará en una carpeta e indicará el nombre y la ruta de acceso del archivo.  
  
8. Haga clic en el mapa está probando y, a continuación, haga clic en **comprobar asignación**.  
  
9. En el X12 **propiedades de instancia EDI** diálogo cuadro, asegúrese de que todas las propiedades sean coherentes con la configuración de las instancias de entrada y salidas.  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se mostrará el **propiedades de instancia EDI** cuadro de diálogo dos veces durante el proceso de comprobación de asignación: una vez para interpretar la instancia de mensaje de entrada y otra para generar la instancia de mensaje de salida. No obstante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede mostrar el cuadro de diálogo más de dos veces, y mostrarlo para esquemas no pertenecientes a EDI. Si es así, haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
10. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Uso de herramientas de XML en tiempo de diseño](../core/using-design-time-xml-tools.md)