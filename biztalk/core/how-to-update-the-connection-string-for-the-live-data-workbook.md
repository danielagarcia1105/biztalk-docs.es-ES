---
title: "Cómo actualizar la cadena de conexión para el libro de datos en directo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d2702fb-637c-46db-8b62-08ae15f983ba
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60de5d1ae904bdefffcf490e3a39d000b28a341d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-connection-string-for-the-live-data-workbook"></a>Cómo actualizar la cadena de conexión del libro de trabajo de datos activos
Cuando mueve la base de datos de importación principal de BAM a otro servidor, la cadena de conexión de un libro de trabajo de datos activos de BAM se debe actualizar para señalar al nuevo servidor. Se utiliza el complemento de BAM para Excel para realizar esta actualización.  
  
### <a name="to-update-the-live-data-workbook-to-point-to-a-new-server"></a>Para actualizar el libro de trabajo de datos activos para que señale a un servidor nuevo  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Office**y, a continuación, haga clic en **Microsoft Office Excel**.  
  
2.  Haga clic en el **archivo** menú y, a continuación, haga clic en **abiertos**. Desplácese hasta el libro de trabajo de datos activos de BAM y haga clic en **abiertos**.  
  
3.  Haga clic en el **BAM** menú en el **Add-Ins** ficha y, a continuación, haga clic en **conexión de base de datos de BAM** para abrir el **Seleccionar base de datos de BAM** cuadro de diálogo.  
  
4.  En el **SQL Server** cuadro de texto, escriba el nombre de SQL server en el que la importación principal de BAM de base de datos ahora reside.  
  
5.  Seleccione la base de datos de importación principal de BAM desde el **nombre de base de datos** lista desplegable.  
  
6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
7.  Guarde el libro de trabajo.  
  
## <a name="see-also"></a>Vea también  
 [Administración de BAM](../core/managing-bam.md)   
 [Requisitos para usar el complemento de BAM para Excel](../core/requirements-for-using-the-bam-add-in-for-excel.md)