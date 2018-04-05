---
title: Cómo utilizar una base de datos como un origen de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: a68057ed-836f-499f-bb80-f644d81bcfc5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a9201ee729288a819a3d527a6ecb4fefd32797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-a-database-as-a-data-source"></a>Cómo utilizar una base de datos como origen de datos
Puede especificar una base de datos como origen de datos. A continuación, puede seleccionar una tabla o columna de tabla de la base de datos y arrastrarla hasta una definición de vocabulario o regla para utilizarla como un hecho.  
  
> [!NOTE]
>  Puede enlazar a la fila o tabla base de datos mediante **DataConnection** o **TypedDataTable** seleccionando "Conexión de datos" o "Tabla o fila de la base de datos" de la **tipo de enlace de la base de datos**  cuadro de lista desplegable en la ventana de propiedades para el **bases de datos** ficha del explorador de hechos. **DataConnection** enlace se usa de forma predeterminada.  
  
### <a name="to-specify-a-sql-database-as-a-data-source"></a>Para especificar una base de datos SQL como origen de datos  
  
1.  En la ventana Explorador de hechos, haga clic en el **bases de datos** ficha.  
  
2.  Haga clic en el **servidores** nodo y, a continuación, haga clic en **examinar**.  
  
3.  Seleccione en la lista desplegable un servidor de base de datos disponible.  
  
4.  Seleccione un tipo de autenticación. Si selecciona autenticación de SQL, escriba un nombre de inicio de sesión y una contraseña. Cuando haya introducido su información de autenticación, haga clic en **Aceptar**.  
  
     ![Captura de pantalla de bases de datos del explorador de árbol. ] (../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")  
Examinar una base de datos  
  
> [!NOTE]
>  No se admiten vistas de la base de datos del servidor SQL Server.