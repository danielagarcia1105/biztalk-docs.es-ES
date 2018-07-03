---
title: Administrar entidades | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.party
helpviewer_keywords:
- Administration Console [BizTalk Server], parties
- managing [parties]
- managing [parties], about managing parties
- parties, managing
ms.assetid: 96d2bcb3-1e38-4dad-a0d6-e5913ba531e7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6f4fb5f56199e694b721acc4af68739275b3cdb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000349"
---
# <a name="managing-parties"></a>Administrar entidades
Mediante el **partes** nodo, puede configurar socios comerciales (entidades) o departamentos internos (perfiles de negocio) con el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] interactúan las soluciones. Para obtener más información, consulte [socios comerciales](../core/trading-partners-and-business-profiles.md).  

Puede crear y configurar una entidad mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Después de crear una entidad en BizTalk Server, es probable que desee interactuar con ella mediante una orquestación. Las entidades interactúan con las orquestaciones mediante funciones. Por ejemplo, una orquestación puede tener definida una función de envío. El remitente tendría una o más entidades asociadas. Cuando la orquestación necesita decidir qué empresa de transporte resulta más económica para efectuar un envío, puede comparar los precios de las entidades presentes en la función de remitente.  

 Es necesario dar de alta la entidad para asociarla a una función específica. Al dar de alta una entidad, ésta podrá interactuar con una orquestación. Consulte [cómo dar de alta o baja una entidad para un rol](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md).

## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

## <a name="create-or-edit-a-party"></a>Crear o editar una entidad

1. Abra **administración de BizTalk Server**.  Expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, haga clic en **partes**, seleccione **New**y, a continuación, seleccione **entidad**.  

2. En el **General** página, realice lo siguiente:  


   |                                                Use                                                 |                                                                                                                                                                                                                                                                      Para                                                                                                                                                                                                                                                                       |
   |---------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                                **Nombre**                                                 |                                                                                                                                                                                                                                                                  Escribir un nombre de entidad.                                                                                                                                                                                                                                                                  |
   | **BizTalk local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** | Active esta casilla para especificar que la entidad representa el mismo socio comercial que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. **Importante:** para que dos entidades TPM solución que usa las canalizaciones de cuadro se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe seleccionar esta casilla para al menos una entidad. **Nota:** si desactiva esta casilla de verificación, algunas propiedades se deshabilitarán mientras cree los acuerdos para esta entidad. |
   |                                **Propiedades adicionales: nombre / valor**                                 |                                                                                                                                                Escriba un par nombre-valor para almacenar cualquier información sobre la entidad. Puede agregar tantos pares nombre-valor como desee. **Tenga en cuenta**: el servidor BizTalk Server no usa los pares de nombre-valor para cualquier procesamiento; estos datos son solo para fines informativos.                                                                                                                                                 |
   |                                               **Eliminar**                                                |                                                                                                                                                                                                                                                    Seleccione esta opción para eliminar el par nombre-valor seleccionado.                                                                                                                                                                                                                                                     |


3. En el **puertos de envío** página, realice lo siguiente.  

   > [!NOTE]
   >  En BizTalk Server, la asociación de puertos de envío se realiza en el nivel de acuerdo. El **puertos de envío** disponible como parte de las propiedades de entidad es para mantener la compatibilidad de la página. Siempre que asocie un puerto de envío con un acuerdo, la configuración del puerto de envío se propaga a la configuración de la entidad y también se puede ver la asociación de puerto de envío en esta página. Sin embargo, el proceso inverso no es verdadero. No se puede asociar un puerto de envío con una entidad y, después, hacer que ese puerto de envío esté automáticamente disponible como parte de la configuración del acuerdo.  

   |       Use        |                                      Para                                       |
   |-----------------------|---------------------------------------------------------------------------------------|
   | **Puertos de envío - nombre** |          Seleccionar en la lista desplegable un puerto de envío para enlazarlo con la entidad.           |
   | **Puertos de envío - URI**  |                            Ver la dirección del puerto de envío.                            |
   |      **Quitar**       |                Seleccione esta opción para quitar el puerto de envío seleccionado de la entidad.                |
   |    **Propiedades**     | Seleccione esta opción para mostrar el **propiedades de puerto de envío** cuadro de diálogo para el puerto de envío seleccionado. |


4. En el **certificado** página, realice lo siguiente:  


   |        Use        |                                                                                                                                                 Para                                                                                                                                                 |
   |------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       **Examinar**       |                                                Seleccione esta opción para mostrar el **Seleccionar certificado** cuadro de diálogo, donde podrá seleccionar el certificado de firma desde el almacén de certificados equipo Local u otras personas a aplicar a los mensajes transmitidos a la entidad.                                                 |
   |    **Nombre común**     |                                                                                                                            Ver una descripción del certificado seleccionado.                                                                                                                             |
   |     **Huella digital**     | Ver la huella digital del certificado de clave privada utilizado para la resolución de la entidad y la comprobación de la firma. La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la a F. |
   | **Quitar certificado** |                                                                                                                                Seleccione esta opción para quitar el certificado que se muestra.                                                                                                                                 |


5. Seleccione **aplicar** para aceptar las propiedades, o seleccione **Aceptar** para completar la opción de configuración. Cualquier acción validará la configuración.  

### <a name="update-an-existing-party"></a>Actualizar una entidad existente
Una vez que la entidad esté dada de alta en una función y los puertos estén enlazados, podrá:  

- Editar el nombre y la descripción de la entidad  
- Editar certificado de la entidad  
- Especifique si la entidad está disponible para la organización que hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]

1. En **administración de BizTalk Server**y seleccione **partes**.

2. En el **entidades y perfiles empresariales** panel, con el botón secundario en la entidad que desea ver o editar y, a continuación, seleccione **propiedades**.  

3. Ver o editar las propiedades. 

4. Seleccione **aplicar** para aceptar las propiedades, o seleccione **Aceptar** para completar la opción de configuración. Cualquier acción validar la configuración.  

## <a name="delete-a-party"></a>Eliminar una entidad
Eliminar la entidad desde la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

> [!IMPORTANT]
>  Sólo se pueden eliminar entidades que no estén dadas de alta en una función. Para poder eliminar una entidad, debe darla de baja primero en las funciones en las que esté dada de alta. Consulte [cómo dar de alta o baja una entidad para un rol](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md). 

1. En **administración de BizTalk Server**, seleccione **partes**, haga clic en la entidad que desea eliminar y, a continuación, seleccione **eliminar**.  

2.  En el **Confirmar eliminación de entidad** cuadro de diálogo, seleccione **Sí** para eliminar la entidad.  

## <a name="search-for-a-party"></a>Buscar una entidad
Si tiene un gran número de entidades creadas, puede usar el **búsqueda** opción para mostrar las entidades que desea ver.  

1. En **administración de BizTalk Server**, seleccione **partes**.

2. En el **entidades y perfiles empresariales** panel hacia la esquina superior derecha, escriba una cadena de búsqueda en el **buscar entidad** cuadro de texto y seleccione el icono de búsqueda. También puede presionar ENTRAR para iniciar la búsqueda.  

    Al usar la función de búsqueda, debe tener en cuenta los puntos siguientes:  

   - La cadena de búsqueda no distingue mayúsculas de minúsculas

   - Puede buscar texto dentro del nombre (búsqueda de subcadenas). Por ejemplo, si busca la cadena ‘int’, la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] muestra tanto las entidades que comienzan con la cadena de búsqueda (p.ej. Intérprete) como las que contienen dicha cadena en el nombre (p.ej. Pintor).  

   - La operación de búsqueda se limita a los nombres de entidad.  

3. Para borrar los resultados de búsqueda, seleccione la 'x' roja junto al cuadro de texto de búsqueda.  

## <a name="see-also"></a>Vea también  
 [Administrar vínculos de rol](../core/managing-role-links.md)   
 [Cómo configurar el componente de canalización de resolución de entidades](../core/how-to-configure-the-party-resolution-pipeline-component.md)  
 [Administrar soluciones EDI y AS2](../core/managing-edi-and-as2-solutions.md)