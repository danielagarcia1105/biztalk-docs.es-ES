---
title: "Trabajar en el Diseñador de orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, saving
- deleting, orchestrations
- projects, orchestrations
- orchestrations, properties
- orchestrations, creating
- creating, orchestrations
- naming conventions, orchestrations
- orchestrations, naming conventions
- orchestrations, deleting
ms.assetid: 13e72b41-d9b6-4508-9a44-b3c7c1804f36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52eb574f9f6b55b784357ff03c05ccb23774fecb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="working-in-orchestration-designer"></a>Trabajar en el Diseñador de orquestaciones
Después de iniciar un proyecto de BizTalk, puede crear nuevas orquestaciones y agregar otras existentes al proyecto. En los procedimientos siguientes se explica cómo crear y guardar una orquestación, agregar una orquestación existente a un proyecto o quitarla de él, cambiar el nombre de una orquestación y establecer las propiedades de orquestación.  
  
### <a name="to-create-an-orchestration"></a>Para crear una orquestación  
  
1.  En el Explorador de soluciones, haga clic en el nombre del proyecto, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, en la **categorías** panel, haga clic en **elementos de proyecto de BizTalk**y, a continuación, en la **plantillas** panel, haga clic en **Orquestación de BizTalk**.  
  
3.  En el **nombre** cuadro en la parte inferior del cuadro de diálogo, proporcione un nombre para la orquestación y, a continuación, haga clic en **agregar**.  
  
     Se crea la nueva orquestación y se muestra en el Diseñador de orquestaciones; además, el archivo .odx correspondiente se crea y muestra en el Explorador de soluciones.  
  
### <a name="to-add-an-existing-orchestration-to-a-project"></a>Para agregar una orquestación existente a un proyecto  
  
1.  En el Explorador de soluciones, haga clic en el nombre del proyecto, haga clic en **agregar**y, a continuación, haga clic en **elemento existente**.  
  
2.  En el **Agregar elemento existente** cuadro de diálogo, desplácese al directorio que contiene la orquestación, seleccione la orquestación y, a continuación, haga clic en **agregar**.  
  
     Se agregará la orquestación al proyecto.  
  
    > [!NOTE]
    >  Si agrega un archivo existente, éste se copia en el proyecto (no solo se agrega mediante referencia). Si cambia el archivo en el proyecto, el archivo original permanece sin cambios.  
  
### <a name="to-change-the-name-of-an-orchestration"></a>Para cambiar el nombre de una orquestación  
  
1.  En el Explorador de soluciones, haga clic en el archivo .odx desea cambiar y, a continuación, haga clic en **cambiar el nombre de**.  
  
2.  Escriba un nuevo nombre de archivo y presione ENTRAR.  
  
    > [!NOTE]
    >  Al cambiar el nombre de un archivo .odx, también puede cambiar el nombre del tipo de orquestación haciendo clic en la superficie de diseño para que aparezca la ventana Propiedades y cambiar el valor de la **Typename** propiedad de la orquestación.  
  
### <a name="to-save-an-orchestration"></a>Para guardar una orquestación  
  
-   En el **archivo** menú, haga clic en **guardar \<nombre de la orquestación\>**.  
  
    > [!NOTE]
    >  Archivos de orquestación se guardan como UTF-8.  Esquemas, asignaciones y canalizaciones se guardan como UTF-16.  
  
### <a name="to-remove-an-orchestration-from-a-project"></a>Para quitar una orquestación de un proyecto  
  
-   En el Explorador de soluciones, haga clic en el archivo que desea quitar y, a continuación, haga clic en **excluir del proyecto**.  
  
    > [!NOTE]
    >  Para quitar la orquestación de un proyecto y eliminar permanentemente el archivo, haga clic en **eliminar** en su lugar.  
  
### <a name="to-include-an-excluded-orchestration-in-a-project"></a>Para incluir una orquestación excluida en un proyecto  
  
-   En el Explorador de soluciones, haga clic en el **mostrar todo** botón de barra de herramientas, menú contextual del archivo .odx deseado y seleccione **incluir en el proyecto**.  
  
### <a name="to-set-orchestration-properties"></a>Para establecer las propiedades de orquestación  
  
1.  Abra la orquestación haciendo doble clic en el archivo .odx del proyecto o seleccionando la pestaña que contiene la orquestación en el área de proceso.  
  
2.  En la ventana Vista orquestación, seleccione **propiedades de orquestación**.  
  
     : "O":  
  
     Haga clic en el **área de proceso** fondo de la superficie de diseño de orquestación.  
  
3.  En la ventana Propiedades, especifique las siguientes propiedades. Tenga en cuenta que algunas propiedades solo aparecen en determinadas circunstancias.  
  
    > [!NOTE]
    >  Los nombres de las orquestaciones, los tipos de puerto y los tipos de mensaje de varias partes deben ser únicos en el ámbito de un módulo.  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Lote|Determina si una orquestación que es una transacción atómica se puede procesar por lotes con otras instancias.|  
    |Compensación|Especifica qué tipo de compensación debe realizarse en la orquestación.|  
    |Nivel de aislamiento|Para las orquestaciones transaccionales, determina el nivel de acceso a los datos para las transacciones simultáneas.|  
    |Exportable a módulo|Determina si el módulo se puede exportar BPEL4WS.|  
    |Target Namespace XML de módulo|Espacio de nombres de destino XML que se usa al exportar tipos a BPEL4WS.|  
    |Espacio de nombres|Determina el nombre del módulo contenedor que incluye la orquestación y los tipos de orquestación.|  
    |Exportable a orquestación|Indica si esta orquestación se podrá exportar a BPEL4WS.|  
    |Target Namespace XML de orquestación|Espacio de nombres de destino XML que se usa al exportar esta orquestación a BPEL4WS.|  
    |Reintentar|Especifica si se reintentará una orquestación transaccional en caso de error.|  
    |Timeout|Tiempo en segundos transcurrido hasta que se produzca un error en la orquestación transaccional por inactividad.|  
    |Identificador de transacción|Identificador único de una orquestación transaccional.|  
    |Tipo de transacción|Determina si la orquestación es una transacción atómica, una transacción de larga ejecución o no tiene transacciones.|  
    |Modificador de tipo|Determina el ámbito de las variables de la orquestación:<br /><br /> Privado: acceso a esta orquestación está limitado al módulo contenedor.<br /><br /> Público: acceso a esta orquestación no está limitado.<br /><br /> Interno: acceso a esta orquestación está limitado a los módulos dentro del mismo proyecto.|  
    |Nombre de tipo|Determina el nombre de esta orquestación en el módulo contenedor. **Nota:** si usar un nombre de tipo que es el mismo que un espacio de nombres de nivel de raíz, puede recibir un error del Diseñador de orquestaciones al definir mensajes y variables basadas en el nombre de tipo e intentar realizar operaciones de asignación con ellos. Por ejemplo, si especifica el nombre de tipo System, y define mensajes y variables cuyo nombre sea, por ejemplo, System.String, podría recibir un error.|  
  
## <a name="see-also"></a>Vea también  
 [Formas de orquestación](../core/orchestration-shapes.md)   
 [Cómo agregar formas a orquestaciones](../core/how-to-add-shapes-to-orchestrations.md)   
 [Cómo agregar parámetros a orquestaciones](../core/how-to-add-parameters-to-orchestrations.md)   
 [Cómo usar el cuadro de diálogo de tipo de artefacto Select](../core/how-to-use-the-select-artifact-type-dialog-box.md)