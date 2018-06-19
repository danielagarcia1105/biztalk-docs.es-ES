---
title: Configurar el entorno | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f0c63671833a394e0c750561d90c12c6476515f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961898"
---
# <a name="setting-the-environment"></a>Configurar el entorno
**Para establecer el entorno:**  
  
1.  Asegúrese de que está configurado el paquete de mensajes de SWIFT. Consulte la documentación del módulo de mensaje Swift para configurar el mismo.  
  
2.  Ejecute el script SQL  *\<unidad\>*: \Program Acelerador de BizTalk para SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql. Cambiar el nombre de base de datos en la secuencia de comandos sql si el Swift y MessagePack están configuradas para el nombre de la base de datos que no sea de A4Swift.  
  
3.  Establezca el valor de clave "origen de datos" como ComputerName y la clave "database" como nombre de base de datos (para el que está configurado el Swift y MessagePack) en el archivo  *\<unidad\>*: \Program BizTalk Acelerador para SWIFT\SDK\Tools\DataImport\DataImport.exe.config.  
  
    > [!NOTE]
    >  El archivo de entrada de datos no debe estar en la misma carpeta que el archivo DataImport.exe.  
  
4.  Ejecute la utilidad DataImport para importar datos en tablas BICplusIBAN y SEPA.