---
title: "Lección 8: Crear e implementar el ensamblado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 607b3a304260e67a6640e579924705719ff8b850
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a>Lección 8: Crear e implementar el ensamblado
En esta lección, generará e implementará el proyecto de canalización para generar un ensamblado que contiene las canalizaciones que creó en los pasos anteriores. En esta lección asegure que no haya ningún error de compilación en el trabajo que ha creado hasta ahora.  
  
 Compilar el proyecto en un archivo de ensamblado (DLL) y guárdelo en el \< *unidad*\>: \Program Acelerador de BizTalk para la carpeta SWIFT\bin\Development.  
  
### <a name="to-build-and-deploy-the-project"></a>Procedimiento para generar e implementar el proyecto  
  
1.  En el Explorador de soluciones, haga clic en **SWIFTPipelines**y, a continuación, haga clic en **generar**.  
  
    > [!NOTE]
    >  Durante el proceso de compilación, no debería ver los errores. Si lo hace, compruebe el origen del error, corríjalo y, a continuación, volver a compilar el proyecto. Sin embargo, puede, aparece un número de advertencias relacionadas con los componentes de canalización de A4SWIFT. Puede corregir la condición que conduce a estas advertencias estableciendo la **Copy Local** propiedades de las referencias al componente de canalización **False**. Para obtener más información, vea "Crear un proyecto de canalización podrían producir advertencias de" en [varios problemas conocidos](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).  
  
2.  Para comprobar la creación de la SWIFTPipelines.dll de archivos, con [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a \< *unidad*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development y asegúrese de que el archivo existe en Esta carpeta.  
  
3.  En el Explorador de soluciones, haga clic en **SWIFTPipelines**y, a continuación, haga clic en **implementar**.  
  
    > [!NOTE]
    >  Durante el proceso de implementación, no debería ver los errores o advertencias. Si lo hace, compruebe el origen del error, corríjalo y, a continuación, vuelva a implementar el proyecto.  
  
4.  Para que se ajuste el éxito de la implementación, en la **vista** menú de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **el Explorador de BizTalk**.  
  
5.  Haga clic en **bases de datos de configuración de BizTalk**y, a continuación, haga clic en **actualizar**.  
  
6.  Expanda el **ensamblados** nodo y confirme que han implementado correctamente el Acelerador **SWIFTPipelines (1.0.0.0)**.  
  
 Continúe con [módulo 4: creación de XML de recepción y puertos de envío de archivo sin formato](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md).