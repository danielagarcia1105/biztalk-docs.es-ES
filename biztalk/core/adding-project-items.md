---
title: Agregar elementos de proyecto | Documentos de Microsoft
description: Agregar las orquestaciones, esquemas, asignaciones y canalizaciones a su proyecto de BizTalk Server en Visual Studio
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1b922d5-8ece-4e1a-a390-e6ae1222665a
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef998865a1851e546a3648b60e0141b3cd137c1b
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="add-project-items"></a>Agregar elementos de proyecto
En el contexto del sistema del proyecto de BizTalk, un elemento de proyecto es un elemento configurado, por ejemplo, una asignación o un esquema. Una aplicación de BizTalk puede contener una o más orquestaciones, esquemas, asignaciones y canalizaciones.  
  
> [!NOTE]
>  Cuando agregue un elemento a un proyecto, no utilice puntos (.) en el nombre, ya que los puntos son separadores en el espacio de nombres .NET. Si usa un punto en el nombre de elemento, el Nombre de tipo del elemento tendrá un carácter de subrayado (_) en lugar de un punto.  
  
> [!NOTE]
>  Cuando se agrega un esquema, un mapa o una canalización en una carpeta, el **nombre completo** propiedad se genera automáticamente e incluye el espacio de nombres y el tipo.  
  
## <a name="orchestrations"></a>Orquestaciones  
 Una orquestación es una representación de un proceso empresarial expresada en lenguaje XLANG/s. XLANG/s puede usarse para complementar lenguajes de procedimiento existentes, como Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] y Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)].  
  
 El Diseñador de orquestaciones se puede utilizar para crear las orquestaciones que desea incluir en un proyecto de BizTalk. Todas las orquestaciones que cree en el Diseñador de orquestaciones tienen la extensión de archivo .odx.  
  
## <a name="schemas"></a>Esquemas  
 Un esquema es la definición de la estructura de un documento o mensaje. Contiene información de la propiedad ya que pertenece a los registros y campos dentro de la estructura. Cuando corresponda, un esquema puede contener varios subesquemas.  
  
 Puede utilizar el Editor de BizTalk para importar, modificar o crear esquemas. Los esquemas que cree puede utilizarlos para generar asignaciones en el Asignador de BizTalk. Todos los esquemas que guarde con el Editor de BizTalk tendrán una extensión de archivo .xsd.  
  
 Para obtener más información acerca de los esquemas y el Editor de BizTalk, consulte [crear esquemas de uso del Editor BizTalk](../core/creating-schemas-using-biztalk-editor.md).  
  
## <a name="maps"></a>Mapas  
 Una asignación es un archivo XML que define la correspondencia entre los registros y campos de un esquema y los de otro. Las asignaciones se crean según los estándares del sector, otros estándares (por ejemplo, normativas internas o problemas heredados) o archivos existentes. Puede crearlas cuando desee transformar datos que recibe o envía de un formato a otro. Puede utilizar el Asignador de BizTalk para crear las asignaciones que incluye en los proyectos de BizTalk. Todas las asignaciones que guarde en el Asignador de BizTalk tendrán una extensión de archivo.btm. Para obtener más información sobre el asignador de BizTalk, consulte [crear asignaciones usando asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).  
  
## <a name="pipelines"></a>Canalizaciones  
 La herramienta Diseñador de canalizaciones se utiliza para crear canalizaciones de recepción y de envío. Una canalización es una infraestructura de software que define y vincula una o varias fases para procesar los mensajes recibidos o enviados por el servidor BizTalk Server. Las canalizaciones implementan las fases en un orden específico e incluyen funciones de codificación o descodificación, ensamblado o desensamblado, y cifrado o descifrado.  
  
 Las referencias predeterminadas de canalización que se incluyen en un proyecto de BizTalk solo pueden procesar documentos XML. Si desea procesar archivos sin formato, documentos EDI u otros tipos de archivo, debe crear las nuevas canalizaciones que correspondan. Todas las canalizaciones que se creen con el Diseñador de canalizaciones tienen la extensión .btp. Para obtener más información acerca de las canalizaciones y el Diseñador de canalizaciones, consulte [crear canalizaciones mediante canalización el diseñador](../core/creating-pipelines-using-pipeline-designer.md).  
  
## <a name="valid-files-for-biztalk-projects"></a>Archivos válidos para proyectos de BizTalk  
 Cuando trabaja con proyectos de BizTalk, puede incluir muchos archivos diferentes, como por ejemplo archivos HTML, archivos XML, archivos de canalización de recepción y archivos de esquema. Con BizTalk Server, el ensamblado puede contener cualquier objeto admitido por el sistema de compilación de Visual Studio.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con proyectos de BizTalk](../core/working-with-biztalk-projects.md)