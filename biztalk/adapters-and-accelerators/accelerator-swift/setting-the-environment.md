---
title: Configurar el entorno | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43027efc-acec-4110-96bd-cc4a19daaeab
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c91221162cccb7b6821c0edad12f8e76de2f10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-environment"></a><span data-ttu-id="968d3-102">Configurar el entorno</span><span class="sxs-lookup"><span data-stu-id="968d3-102">Setting the Environment</span></span>
<span data-ttu-id="968d3-103">**Para establecer el entorno:**</span><span class="sxs-lookup"><span data-stu-id="968d3-103">**To set the environment:**</span></span>  
  
1.  <span data-ttu-id="968d3-104">Asegúrese de que está configurado el paquete de mensajes de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="968d3-104">Make sure SWIFT Message Pack is configured.</span></span> <span data-ttu-id="968d3-105">Consulte la documentación del módulo de mensaje Swift para configurar el mismo.</span><span class="sxs-lookup"><span data-stu-id="968d3-105">Refer to the Swift Message Pack documentation to configure the same.</span></span>  
  
2.  <span data-ttu-id="968d3-106">Ejecute el script SQL  *\<unidad >*: \Program Acelerador de BizTalk para SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql.</span><span class="sxs-lookup"><span data-stu-id="968d3-106">Run the SQL script *\<drive>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\CreateProceduresScript.sql.</span></span> <span data-ttu-id="968d3-107">Cambiar el nombre de base de datos en la secuencia de comandos sql si el Swift y MessagePack están configuradas para el nombre de la base de datos que no sea de A4Swift.</span><span class="sxs-lookup"><span data-stu-id="968d3-107">Change the database name in the sql script if the Swift and MessagePack are configured for database name other than A4Swift.</span></span>  
  
3.  <span data-ttu-id="968d3-108">Establecer el valor de clave "origen de datos" como ComputerName y la clave "database" como nombre de base de datos (para el que está configurado el Swift y MessagePack) en el archivo  *\<unidad >*: \Program Acelerador de BizTalk para SWIFT\SDK\Tools\DataImport\DataImport.exe.config.</span><span class="sxs-lookup"><span data-stu-id="968d3-108">Set the value of Key “datasource” as ComputerName and key “database” as database name (for which the Swift and MessagePack is configured) in the file *\<drive>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools\DataImport\DataImport.exe.config.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="968d3-109">El archivo de entrada de datos no debe estar en la misma carpeta que el archivo DataImport.exe.</span><span class="sxs-lookup"><span data-stu-id="968d3-109">The data input file should not be in the same folder as the DataImport.exe file.</span></span>  
  
4.  <span data-ttu-id="968d3-110">Ejecute la utilidad DataImport para importar datos en tablas BICplusIBAN y SEPA.</span><span class="sxs-lookup"><span data-stu-id="968d3-110">Run the DataImport utility to import data in BICplusIBAN and SEPA tables.</span></span>