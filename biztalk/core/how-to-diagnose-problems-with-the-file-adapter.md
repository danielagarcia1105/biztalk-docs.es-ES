---
title: "Cómo diagnosticar problemas con el adaptador de archivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f06089a5-4747-4879-a796-157088868dba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0481a3abdf497c093a87d7d74ea0356c7cad0d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a>Cómo diagnosticar problemas con el adaptador de archivo
Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con el adaptador de archivo.  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a>Ejecutar la utilidad FileMon para diagnosticar errores que se producen al utilizar el adaptador de recepción de archivos o el adaptador de envío de archivos  
  
1.  Descargar la utilidad FileMon de [www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235).  
  
2.  Instale la utilidad Filemon en el servidor que aloja la carpeta o el recurso compartido que va a ser leído o escrito por el adaptador de archivos.  
  
3.  Inicie la utilidad Filemon y aplique un filtro para supervisar solo los accesos a archivos que va a crear la instancia de host de BizTalk que los controles de adaptadores de archivos van a ejecutar en ellos (por ejemplo, BTSNTSvc.exe).  
  
4.  Ejecute el escenario que ha causado el problema.  
  
5.  Deshabilite el archivo que controla en la utilidad Filemon y, a continuación, guarde el archivo de registro generado en el disco.  
  
6.  Revise el archivo de registro generado para comprobar los errores.  
  
    > [!NOTE]
    >  FileMon no es compatible con Microsoft y Microsoft no garantiza la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solucionar problemas del adaptador de archivo](../core/troubleshooting-the-file-adapter.md)