```markdown
# Système de Réservation de Vols API

Ce projet est un système de réservation de vols basé sur des microservices. Le système permet aux clients de consulter les vols, de faire des réservations et de gérer leurs réservations. Le personnel peut gérer les vols, les aéroports, les avions et consulter tous les enregistrements de réservation. Le service principal du projet est : `api_common`.

## Table des Matières

- [Aperçu de l'API](#aperçu-de-lapi)
- [Installation](#installation)
- [Exécution](#exécution)
- [Points de Terminaison](#points-de-terminaison)
  - [Gestion des Utilisateurs](#gestion-des-utilisateurs)
  - [Gestion des Vols](#gestion-des-vols)
  - [Gestion des Réservations](#gestion-des-réservations)
  - [Gestion des Aéroports](#gestion-des-aéroports)
  - [Gestion des Avions](#gestion-des-avions)
  - [Tous les Enregistrements de Réservation](#tous-les-enregistrements-de-réservation)
- [Modèles](#modèles)

## Aperçu de l'API

Cette API intègre toutes les fonctionnalités des clients et du personnel, garantissant que différents rôles d'utilisateurs peuvent accéder à leurs fonctionnalités respectives.

## Installation

1. Cloner le dépôt :
   ```bash
   git clone https://github.com/your_username/your_repository.git
   cd your_repository
   ```

2. Créer et activer un environnement virtuel :
   ```bash
   python -m venv venv
   source venv/bin/activate   # Linux
   venv\Scripts\activate      # Windows
   ```

3. Installer les dépendances :
   ```bash
   pip install -r requirements.txt
   ```

4. Exécuter les migrations de la base de données :
   ```bash
   python manage.py migrate
   ```

## Exécution

Démarrer

 le serveur de développement :
```bash
python manage.py runserver
```

## Points de Terminaison

### Gestion des Utilisateurs

- **Obtenir la liste des utilisateurs (seulement pour les administrateurs)**
  - **Point de Terminaison**: `/api/users/`
  - **Méthode**: GET
  - **Description**: Obtenir la liste de tous les utilisateurs.

- **Mettre à jour un utilisateur**
  - **Point de Terminaison**: `/api/users/<int:pk>/`
  - **Méthode**: PUT
  - **Description**: Mettre à jour les informations d'un utilisateur.

- **Supprimer un utilisateur**
  - **Point de Terminaison**: `/api/users/<int:pk>/`
  - **Méthode**: DELETE
  - **Description**: Supprimer un utilisateur.

### Gestion des Vols

- **Obtenir tous les vols**
  - **Point de Terminaison**: `/api/flights/`
  - **Méthode**: GET
  - **Description**: Obtenir la liste de tous les vols disponibles.

- **Ajouter un nouveau vol (seulement pour le personnel)**
  - **Point de Terminaison**: `/api/flights/`
  - **Méthode**: POST
  - **Description**: Ajouter un nouveau vol.

- **Mettre à jour les informations d'un vol (seulement pour le personnel)**
  - **Point de Terminaison**: `/api/flights/<int:pk>/`
  - **Méthode**: PUT
  - **Description**: Mettre à jour les informations d'un vol.

- **Supprimer un vol (seulement pour le personnel)**
  - **Point de Terminaison**: `/api/flights/<int:pk>/`
  - **Méthode**: DELETE
  - **Description**: Supprimer un vol.

### Gestion des Réservations

- **Obtenir la liste des réservations d'un utilisateur**
  - **Point de Terminaison**: `/api/bookings/`
  - **Méthode**: GET
  - **Description**: Obtenir la liste de toutes les réservations de l'utilisateur authentifié.

- **Obtenir les détails d'une réservation**
  - **Point de Terminaison**: `/api/bookings/<int:pk>/`
  - **Méthode**: GET
  - **Description**: Obtenir les détails d'une réservation spécifique.

- **Créer une nouvelle réservation**
  - **Point de Terminaison**: `/api/bookings/`
  - **Méthode**: POST
  - **Description**: Créer une nouvelle réservation.

- **Mettre à jour une réservation**
  - **Point de Terminaison**: `/api/bookings/<int:pk>/`
  - **Méthode**: PUT
  - **Description**: Mettre à jour les informations d'une réservation.

- **Supprimer une réservation**
  - **Point de Terminaison**: `/api/bookings/<int:pk>/`
  - **Méthode**: DELETE
  - **Description**: Supprimer une réservation.

### Gestion des Aéroports (seulement pour le personnel)

- **Obtenir la liste de tous les aéroports**
  - **Point de Terminaison**: `/api/airports/`
  - **Méthode**: GET
  - **Description**: Obtenir la liste de tous les aéroports.

- **Obtenir les détails d'un aéroport**
  - **Point de Terminaison**: `/api/airports/<int:pk>/`
  - **Méthode**: GET
  - **Description**: Obtenir les détails d'un aéroport spécifique.

- **Ajouter un nouvel aéroport**
  - **Point de Terminaison**: `/api/airports/`
  - **Méthode**: POST
  - **Description**: Ajouter un nouvel aéroport.

- **Mettre à jour les informations d'un aéroport**
  - **Point de Terminaison**: `/api/airports/<int:pk>/`
  - **Méthode**: PUT
  - **Description**: Mettre à jour les informations d'un aéroport.

- **Supprimer un aéroport**
  - **Point de Terminaison**: `/api/airports/<int:pk>/`
  - **Méthode**: DELETE
  - **Description**: Supprimer un aéroport.

### Gestion des Avions (seulement pour le personnel)

- **Obtenir la liste de tous les avions**
  - **Point de Terminaison**: `/api/planes/`
  - **Méthode**: GET
  - **Description**: Obtenir la liste de tous les avions.

- **Obtenir les détails d'un avion**
  - **Point de Terminaison**: `/api/planes/<int:pk>/`
  - **Méthode**: GET
  - **Description**: Obtenir les détails d'un avion spécifique.

- **Ajouter un nouvel avion**
  - **Point de Terminaison**: `/api/planes/`
  - **Méthode**: POST
  - **Description**: Ajouter un nouvel avion.

- **Mettre à jour les informations d'un avion**
  - **Point de Terminaison**: `/api/planes/<int:pk>/`
  - **Méthode**: PUT
  - **Description**: Mettre à jour les informations d'un avion.

- **Supprimer un avion**
  - **Point de Terminaison**: `/api/planes/<int:pk>/`
  - **Méthode**: DELETE
  - **Description**: Supprimer un avion.

### Tous les Enregistrements de Réservation (seulement pour le personnel)

- **Obtenir tous les enregistrements de réservation**
  - **Point de Terminaison**: `/api/all-bookings/`
  - **Méthode**: GET
  - **Description**: Obtenir la liste de toutes les réservations.

## Modèles

Voici les principaux modèles de données utilisés dans ce projet :

- **StaffType**: Type de personnel.
- **Group**: Informations sur les groupes d'utilisateurs.
- **ClientGroups**: Relation entre clients et groupes.
- **StaffGroups**: Relation entre le personnel et les groupes.
- **Permission**: Informations sur les permissions.
- **ClientPermissions**: Relation entre les clients et les permissions.
- **StaffPermissions**: Relation entre le personnel et les permissions.
- **Flight**: Informations sur les vols, y compris le numéro de vol, les heures de départ et d'arrivée, les avions et les itinéraires.
- **Booking**: Informations sur les réservations, y compris la date de réservation, le prix, le type de réservation, le client et le vol.
- **Airport**: Informations sur les aéroports, y compris le nom et la localisation.
- **Plane**: Informations sur les avions, y compris le modèle, la capacité en classe économique et en première classe.
- **Track**: Informations sur les pistes, y compris le numéro de piste, la longueur et l'aéroport auquel elles appartiennent.

N'hésitez pas à contribuer au code, soumettre des problèmes ou des suggestions !
# 航班预订系统 API

本项目是一个基于微服务的航班预订系统。系统允许客户查看航班、进行预订和管理他们的预订。工作人员可以管理航班、机场、飞机，并查看所有的预订记录。项目主要服务：`api_common`。

## 目录

- [API 概述](#api-概述)
- [安装](#安装)
- [运行](#运行)
- [端点](#端点)
  - [用户管理](#用户管理)
  - [航班管理](#航班管理)
  - [预订管理](#预订管理)
  - [机场管理](#机场管理)
  - [飞机管理](#飞机管理)
  - [所有预订记录](#所有预订记录)
- [模型](#模型)

## API 概述

本API整合了所有客户端和工作人员的功能，确保不同用户角色可以访问他们相应的功能。

## 安装

1. 克隆仓库：
   ```bash
   git clone https://github.com/your_username/your_repository.git
   cd your_repository
   ```

2. 创建并激活虚拟环境：
   ```bash
   python -m venv venv
   source venv/bin/activate   # Linux
   venv\Scripts\activate      # Windows
   ```

3. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```

4. 运行数据库迁移：
   ```bash
   python manage.py migrate
   ```

## 运行

启动开发服务器：
```bash
python manage.py runserver
```

## 端点

### 用户管理

- **获取用户列表（仅管理员）**
  - **端点**: `/api/users/`
  - **方法**: GET
  - **描述**: 获取所有用户的列表。

- **更新用户**
  - **端点**: `/api/users/<int:pk>/`
  - **方法**: PUT
  - **描述**: 更新用户详细信息。

- **删除用户**
  - **端点**: `/api/users/<int:pk>/`
  - **方法**: DELETE
  - **描述**: 删除用户。

### 航班管理

- **获取所有航班**
  - **端点**: `/api/flights/`
  - **方法**: GET
  - **描述**: 获取所有可用航班的列表。

- **添加新航班（仅工作人员）**
  - **端点**: `/api/flights/`
  - **方法**: POST
  - **描述**: 添加新航班。

- **更新航班信息（仅工作人员）**
  - **端点**: `/api/flights/<int:pk>/`
  - **方法**: PUT
  - **描述**: 更新航班详细信息。

- **删除航班（仅工作人员）**
  - **端点**: `/api/flights/<int:pk>/`
  - **方法**: DELETE
  - **描述**: 删除航班。

### 预订管理

- **获取用户预订列表**
  - **端点**: `/api/bookings/`
  - **方法**: GET
  - **描述**: 获取当前认证用户的所有预订列表。

- **获取预订详情**
  - **端点**: `/api/bookings/<int:pk>/`
  - **方法**: GET
  - **描述**: 获取特定预订的详细信息。

- **创建预订**
  - **端点**: `/api/bookings/`
  - **方法**: POST
  - **描述**: 创建新预订。

- **更新预订**
  - **端点**: `/api/bookings/<int:pk>/`
  - **方法**: PUT
  - **描述**: 更新预订详细信息。

- **删除预订**
  - **端点**: `/api/bookings/<int:pk>/`
  - **方法**: DELETE
  - **描述**: 删除预订。

### 机场管理（仅工作人员）

- **获取所有机场**
  - **端点**: `/api/airports/`
  - **方法**: GET
  - **描述**: 获取所有机场的列表。

- **获取机场详情**
  - **端点**: `/api/airports/<int:pk>/`
  - **方法**: GET
  - **描述**: 获取特定机场的详细信息。

- **添加机场**
  - **端点**: `/api/airports/`
  - **方法**: POST
  - **描述**: 添加新机场。

- **更新机场信息**
  - **端点**: `/api/airports/<int:pk>/`
  - **方法**: PUT
  - **描述**: 更新机场详细信息。

- **删除机场**
  - **端点**: `/api/airports/<int:pk>/`
  - **方法**: DELETE
  - **描述**: 删除机场。

### 飞机管理（仅工作人员）

- **获取所有飞机**
  - **端点**: `/api/planes/`
  - **方法**: GET
  - **描述**: 获取所有飞机的列表。

- **获取飞机详情**
  - **端点**: `/api/planes/<int:pk>/`
  - **方法**: GET
  - **描述**: 获取特定飞机的详细信息。

- **添加飞机**
  - **端点**: `/api/planes/`
  - **方法**: POST
  - **描述**: 添加新飞机。

- **更新飞机信息**
  - **端点**: `/api/planes/<int:pk>/`
  - **方法**: PUT
  - **描述**: 更新飞机详细信息。

- **删除飞机**
  - **端点**: `/api/planes/<int:pk>/`
  - **方法**: DELETE
  - **描述**: 删除飞机。

### 所有预订记录（仅工作人员）

- **获取所有预订记录**
  - **端点**: `/api/all-bookings/`
  - **方法**: GET
  - **描述**: 获取所有预订记录的列表。

## 模型

以下是本项目使用的主要数据模型：

- **StaffType**: 工作人员类型。
- **Group**: 用户组信息。
- **ClientGroups**: 客户和组的关系。
- **StaffGroups**: 工作人员和组的关系。
- **Permission**: 权限信息。
- **ClientPermissions**: 客户和权限的关系。
- **StaffPermissions**: 工作人员和权限的关系。
- **Flight**: 航班信息，包括航班号、起飞和降落时间、飞机及航线。
- **Booking**: 预订信息，包括预订日期、价格、预订类型、客户及航班。
- **Airport**: 机场信息，包括名称和位置。
- **Plane**: 飞机信息，包括型号、头等舱和经济舱容量。
- **Track**: 跑道信息，包括跑道号、长度和所属机场。

欢迎贡献代码，提交问题或建议！
```

