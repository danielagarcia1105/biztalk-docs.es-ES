---
title: "Cómo volver a generar el libro de datos en directo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3e98ac5f02363c02ff422f44397fbf1f0e3b4c0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-regenerate-the-live-data-workbook"></a>Cómo regenerar el libro de trabajo de datos activos
En caso de pérdida o daño del libro de trabajo de datos activos de BAM, es posible regenerar el libro de trabajo mediante la utilidad de administración de BAM. Este proceso también resulta útil cuando está actualizando desde [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] a BizTalk Server, desde los libros de datos en directo para [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] no son compatibles con BizTalk Server.  
  
 Los pasos generales son los siguientes:  
  
-   Recuperar la definición de BAM de la base de datos de BAM mediante la utilidad de administración de BAM.  
  
-   Volver a crear informes de tabla dinámica. Puesto que la recuperación de XML mediante el comando get-defxml contiene, únicamente, las actividades y las vistas, es preciso volver a crear los informes de tabla dinámica mediante el complemento de BAM para Excel.  
  
-   Cambiar el nombre de los informes de tabla dinámica. Este paso es necesario si va a actualizar desde [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] a BizTalk Server. Esto es necesario porque en [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)], BAM almacena dos conjuntos de nombres para los libros BAM: un nombre para mostrar y un nombre interno. Al recuperar la definición de BAM, el XML contiene el nombre interno del libro de trabajo. Es preciso cambiar el nombre de los informes de tabla dinámica para garantizar que el libro de trabajo de datos activos tenga la conexión adecuada con la base de datos.  
  
-   Regenerar el libro de trabajo de datos activos mediante la utilidad de administración de BAM.  
  
### <a name="to-retrieve-the-bam-definition"></a>Para recuperar la definición de BAM  
  
1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, desplácese al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Tipo: **bm.exe get-defxml-FileName:abc.xml**  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-re-create-the-pivottable-reports"></a>Para volver a crear informes de tabla dinámica  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office**y, a continuación, haga clic en **Microsoft Office Excel**.  
  
2.  Haga clic en el **Add-Ins** pestaña y, a continuación, seleccione **importar XML** desde el **BAM** la lista desplegable en el **comandos de menú** grupo.  
  
    > [!NOTE]
    >  Si el **Add-Ins** ficha no está presente, siga las instrucciones de [paso 1: agregar el complemento de BAM a Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448) para agregar el complemento de BAM.  
  
3.  Desplácese hasta la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking y seleccione el archivo abc.xml.  
  
4.  Vuelva a crear los informes de tabla dinámica basándose en la definición.  
  
5.  Guarde el libro de trabajo. Para ello, haga clic en el **archivo** menú y, a continuación, haga clic en **Guardar como** y escriba mynewbook.xls cuando se le solicite un nombre de archivo.  
  
### <a name="to-rename-the-pivottable-reports-optional"></a>Para cambiar el nombre de los informes de tabla dinámica (opcional)  
  
1.  Abra el archivo abc.xml creado al recuperar las definiciones de BAM con el Bloc de notas haciendo clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\abc y, a continuación, haga clic en  **Aceptar**.  
  
2.  Busque la \<título\> etiqueta en \<BAMDefinition\>\\< extensión\>\\< OWC\>\\< PivotTableView\> \\< tabla dinámica\>\\< PivotView\>\\< etiqueta\>. El contenido de esta etiqueta es el nombre interno de uno de los informes de tabla dinámica. Puede encontrar el nombre interno para que los otros informes de tabla dinámica, localizando el siguiente \<título\> etiqueta. Abra **mynewbook.xls** y usar los nombres encontrados para cambiar el nombre de los informes de tabla dinámica.  
  
3.  Guarde el libro de trabajo actualizado.  
  
    > [!NOTE]
    >  Debe seguir este procedimiento solo si está actualizando desde [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] a BizTalk Server.  
  
### <a name="to-regenerate-the-bam-live-data-workbook"></a>Para regenerar el libro de trabajo de datos activos de BAM  
  
1.  Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, desplácese al directorio siguiente: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3.  Tipo: **bm.exe regenerate-livedataworkbook-WorkbookName:mynewbook.xls**  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)   
 [Requisitos para usar el complemento de BAM para Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md)   
 [Paso 1: Agregar el complemento de BAM a Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)