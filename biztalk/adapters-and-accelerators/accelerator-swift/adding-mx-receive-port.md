---
title: "Puerto de recepción de agregar MX | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4818d6af-df1d-481e-becf-1af633735248
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69123b876bdda4b5f999277a1710cdeb1cb61fe7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-mx-receive-port"></a>Agregar MX de puerto de recepción
**Para agregar un MX de puerto de recepción:**  
  
1.  Iniciar **administración de BizTalk Server** consola.  
  
2.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Aplicación de BizTalk 1**.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el cuadro de diálogo Propiedades de puerto de recepción, en el cuadro Nombre, escriba **puerto de recepción de MX_**.  
  
5.  Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.  
  
6.  Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
7.  En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en **puerto de recepción de MX_**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Propiedades de la ubicación de recepción, en el cuadro Nombre, escriba **ubicación de recepción de MX_**.  
  
9. En la sección transporte, en el cuadro de texto de tipo, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
10. Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
11. En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**y, a continuación, seleccione una ubicación de archivo.  
  
12. En el cuadro de diálogo Propiedades de transporte de archivo, asegúrese de que \*.xml se escribe en el cuadro de máscara de archivo y, a continuación, haga clic en **Aceptar**.  
  
13. En el cuadro de diálogo Propiedades de la ubicación de recepción, asegúrese de que BizTalkServerApplication se haya especificado para el cuadro de controlador de recepción.  
  
14. En el cuadro de la canalización de recepción, seleccione **canalización de recepción** (la canalización de recepción que se ha implementado en el proyecto de canalización) en la lista desplegable, haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
15. Haga clic en la ubicación que acaba de configurar y, a continuación, haga clic en **habilitar**.