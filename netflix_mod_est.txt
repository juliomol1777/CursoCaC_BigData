USE `netflix`;
DROP TABLE IF EXISTS `oscar`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;

CREATE TABLE `content` (
  `id_content` int NOT NULL AUTO_INCREMENT,
  `type` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `title_content` varchar(64) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `director` varchar(64) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `cast` varchar(1024) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `country` varchar(128) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `date_added` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `release_year` int DEFAULT NULL,
  `rating` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `duration` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `listed_in` varchar(128) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `description` varchar(256) COLLATE utf8mb4_general_ci DEFAULT NULL,
  PRIMARY KEY (`id_content`)
) ENGINE=InnoDB AUTO_INCREMENT=8808 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
/*!40101 SET character_set_client = @saved_cs_client */;


CREATE TABLE `production` (
  `id_production` int NOT NULL AUTO_INCREMENT,
  `id_content` int DEFAULT NULL,
  `title_production` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `genre` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `premiere` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `runtime` int DEFAULT NULL,
  `imdb_score` double DEFAULT NULL,
  `language` varchar(50) COLLATE utf8mb4_general_ci DEFAULT NULL,
  PRIMARY KEY (`id_production`),
  KEY `content_id` (`id_content`),
  CONSTRAINT `productions_ibfk_1` FOREIGN KEY (`id_content`) REFERENCES `content` (`id_content`)
) ENGINE=InnoDB AUTO_INCREMENT=563 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
/*!40101 SET character_set_client = @saved_cs_client */;



CREATE TABLE `oscar` (
  `id_oscar` int NOT NULL AUTO_INCREMENT,
  `id_inf` int DEFAULT NULL,
  `id_res` int DEFAULT NULL,
  `id_content` int DEFAULT NULL,
  `title_oscar` varchar(128) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `year_ceremony` int DEFAULT NULL,
  `category` varchar(256) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `name` varchar(256) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `winner` tinyint DEFAULT NULL,
  `directed_by` varchar(128) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `based_on` varchar(512) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `starring` varchar(512) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `distributed_by` varchar(256) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `budget` varchar(128) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `budget_x_million` double DEFAULT NULL,
  `box_office` varchar(128) COLLATE utf8mb4_general_ci DEFAULT NULL,
  `box_office_x_million` double DEFAULT NULL,
  `imdb` double DEFAULT NULL,
  `metascore` int DEFAULT NULL,
  `rotten_tomatoes` int DEFAULT NULL,
  PRIMARY KEY (`id_oscar`)
) ENGINE=InnoDB AUTO_INCREMENT=8808 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
