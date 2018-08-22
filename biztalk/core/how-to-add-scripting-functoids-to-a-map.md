---
title: Cómo agregar Functoids de Scripting a una asignación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.script
ms.assetid: eb96814a-b3fb-48f6-a947-ab595a270faa
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e983564b448ef27323879c6db15ccc232d032d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019142"
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a>Cómo agregar functoids de secuencia de comandos a una asignación
El **Scripting** functoid le permite usar un script personalizado o código en tiempo de ejecución para realizar funciones de lo contrario, no está disponibles. Por ejemplo, se puede llamar a un objeto COM en tiempo de ejecución mediante la **Scripting** functoid y escribir su propio script personalizado.  
  
 Para obtener información conceptual sobre la **Scripting** functoid, consulte [Functoid de Scripting](../core/scripting-functoid.md).  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a>Para agregar el functoid de secuencia de comandos a una asignación y configurarlo  
  
1. Con el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el activa, haga clic en cuadro de herramientas del **Functoids avanzados** tab para seleccionar esa categoría de functoids.  
  
    Aparece la lista de functoids avanzados de la categoría seleccionada.  
  
2. Arrastre el **Scripting** functoid ![](../core/media/bts-tls-scripting.gif "bts_tls_scripting") desde el cuadro de herramientas hasta la ubicación adecuada en una página de cuadrícula.  
  
   > [!NOTE]
   >  El functoid se colocará en la página de cuadrícula mostrada. Si desea colocar el functoid en una página de cuadrícula diferente, deberá mostrar otra página de cuadrícula en primer lugar.  
  
   > [!NOTE]
   >  Si se construye un mapa con más de un functoid juntas, necesitará tener en cuenta su ubicación relativa de izquierda a derecha. Los functoids se ejecutan de izquierda a derecha. La salida de un functoid solo puede ser la entrada a otro functoid que esté situado más a la derecha.  
  
3. Seleccione el **Scripting** functoid que acaba de agregar a la página de cuadrícula mostrada.  
  
4. En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) botón asociado a la **Script** propiedad.  
  
   > [!NOTE]
   >  Como alternativa, haga clic en el functoid y, a continuación, haga clic en **Configurar secuencia de comandos de Functoid** en el menú contextual. El **configurar Functoid de script** aparece el cuadro de diálogo con el **configuración de Functoid de secuencia de comandos** pestaña seleccionada.  
  
5. En el **configurar Functoid de script** cuadro de diálogo el **Seleccionar tipo de script** lista desplegable, seleccione el tipo de la secuencia de comandos.  
  
   > [!NOTE]
   >  Según el tipo de secuencia de comandos que elija, se habilitarán y deshabilitará distintos subconjuntos de los demás campos del cuadro de diálogo.  
  
6. Si seleccionó **ensamblado externo** como el tipo de secuencia de comandos, use el **ensamblado de Script**, **clase de Script**, y **método de Script** desplegable las listas, en ese orden, para seleccionar el ensamblado, clase y método, respectivamente, para asociarlos con este **Scripting** functoid.  
  
   > [!WARNING]
   >  El código del ensamblado externo debe ser seguro para subprocesos. En condiciones de sobrecarga, pueden ejecutarse simultáneamente varias instancias de una asignación.  
  
   > [!NOTE]
   >  Después de haber seleccionado un ensamblado, el **clase de Script** se rellenará la lista desplegable con las clases de ese ensamblado. Del mismo modo, después de haber seleccionado una clase, el **método de Script** se rellenará la lista desplegable con los métodos de esa clase.  
  
   > [!NOTE]
   >  El **script en línea** cuadro de texto se deshabilita cuando selecciona **ensamblado externo** como el tipo de secuencia de comandos.  
  
    Si seleccionó algo distinto **ensamblado externo** como el tipo de secuencia de comandos (una de las opciones en línea), use el **script en línea** cuadro de texto para escribir el script en el idioma seleccionado.  
  
   > [!NOTE]
   >  Las opciones de idioma en línea para la **Scripting** functoid incluyen C#. NET, JScript.NET, Visual Basic. NET, XSLT y plantilla de llamada XSLT.  
  
    Los scripts que usan C# no permiten declaraciones "using". Si el script debe usar alguna clase .Net especial. A continuación, los ensamblados correspondientes y sus ensamblados dependientes debe agregarse a "Referencias" en el proyecto de BizTalk y el código del script debe usar nombres completos. Si escribe un script para realizar la conversión de minúsculas sensible a cultura, el fragmento de código correspondiente debe escribirse tal como se indica a continuación. Se aplican limitaciones similares a todos los lenguajes de script admitidos.  
  
   ```  
   string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
   ```  
  
    En el script, para usar clases de cualquier ensamblado, asegúrese de agregar el ensamblado correspondiente y sus ensamblados dependientes a “Referencias” en el proyecto de BizTalk que contiene la asignación.  
  
   > [!NOTE]
   >  Puede crear un script personalizado directamente en el **script en línea** cuadro de texto, o se puede crear el script en otra parte y péguelo en el **script en línea** cuadro de texto.  
  
   > [!NOTE]
   >  El **ensamblado de Script**, **clase de Script**, y **método de Script** listas desplegables se deshabilitan cuando selecciona una de las opciones en línea (algo que no sea **Ensamblado externo**) como el tipo de secuencia de comandos.  
  
   > [!IMPORTANT]
   >  Si crea una secuencia de comandos que contenga varias funciones, la primera función se considerará como la principal o primaria; las demás solo se llamarán si son necesarias para la ejecución de la función principal.  
  
    Haga clic en **Aceptar**.  
  
7. Si la secuencia de comandos o el método asociado en un ensamblado externo requieren parámetros de entrada, cree el número y el tipo de vínculos de entrada apropiados de igual modo que para un functoid básico.  
  
8. En la mayoría de los casos, su **Scripting** functoid generará un valor de salida utilizado para rellenar un campo del esquema de destino, o como entrada para otro functoid, prácticamente la misma manera que functoids básicos hacer.  
  
## <a name="see-also"></a>Vea también  
 [Agregar functoids avanzados a una asignación](../core/adding-advanced-functoids-to-a-map.md)