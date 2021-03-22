---
title: Assignment 1
subtitle: Computer performance, reliability, and scalability calculation
author: Vinay Nagaraj
---

## 1.2 

#### a. Data Sizes

| Data Item                                  | Size per Item |
|--------------------------------------------|--------------:|
| 128 character message.                     | 128 Bytes     |  
| 1024x768 PNG image                         | 1.5 MB        |
| 1024x768 RAW image                         | 2.25 MB       | 
| HD (1080p) HEVC Video (15 minutes)         | 160 MB        |
| HD (1080p) Uncompressed Video (15 minutes) | 160,180 MB    |
| 4K UHD HEVC Video (15 minutes)             | 640 MB        |
| 4k UHD Uncompressed Video (15 minutes)     | 640,720 MB    |
| Human Genome (Uncompressed)                | 1.5 GB        |

Reference:<br />
1. 1 character is 1 byte. https://www.unitconverters.net/data-storage/character-to-byte.htm<br />
2. ((1024 * 768 * 16 bit)) / ( 8 * 1024)) / 1024 =  1.5 MB<br />
3. ((1024 * 768 * 24 bit)) / ( 8 * 1024)) / 1024 =  2.25 MB<br />
4. (1920 * 1080 * 24 bit * 30 fps * 900 duration in seconds) = (1,343,692,800,000 / 8192) = (164,025,000 KB / 1024) = (160,180 MB / 1000) = 160 MB<br />
5. (1920 * 1080 * 24 bit * 30 fps * 900 duration in seconds) = (1,343,692,800,000 / 8192) = (164,025,000 KB / 1024) = 160,180 MB<br />
6. For 4K UHD, the dimensions is 3840 * 2160 instead of 1920 * 1080. So the size will be 4 times the HD video size. 160 * 4 = 640MB<br />
7. 160,180 * 4 = 640,720 MB<br />
8. https://bitesizebio.com/8378/how-much-information-is-stored-in-the-human-genome/ <br /><br />


#### b. Scaling

|                                           | Size     | # HD | 
|-------------------------------------------|---------:|-----:|
| Daily Twitter Tweets (Uncompressed)       | 64GB     |    1 |
| Daily Twitter Tweets (Snappy Compressed)  | 37.647GB |    1 |
| Daily Instagram Photos                    | 112.5 TB |   34 |
| Daily YouTube Videos                      | 460.8 TB |  139 |
| Yearly Twitter Tweets (Uncompressed)      | 23.36 TB |    8 |
| Yearly Twitter Tweets (Snappy Compressed) | 13.74 TB |    5 |
| Yearly Instagram Photos                   | 41 PB    |12319 |
| Yearly YouTube Videos                     | 168.2 PB |50458 |

Reference:<br />
1. 500,000,000 * 128 bytes = 64GB<br />
2. 64GB / 1.7 = 37.647GB<br />
3. 75 Million Photos * 1.5 MB PNG Image = 112.5 TB. <br />
    112.5 * 0.3 = 33.75 HDD.<br />
4. 500hrs * 60mins = 30000mins. 15 min = 160MB, 30000mins = 320,000 MB. So we have 320GB per min. 320 * 60 * 24 = 460,800 GB.<br />
    460.8 * 0.3 = 138.24 HDD<br />
5. 64 * 365 = 23360 GB.<br />
    23.36 * 0.3 = 7.008<br />
6. 37.647 * 365 = 13741GB<br />
    13.74 * 0.3 = 4.122<br />
7. 112.5 * 365 = 41062.5 TB<br />
    41062.5 * 0.3 = 12318.75<br />
8. 460.8 * 365 = 168192 TB<br />
    168192 * 0.3 = 50457.6<br /><br />

#### c. Reliability
|                                    | # HD | # Failures |
|------------------------------------|-----:|-----------:|
| Twitter Tweets (Uncompressed)      | 8    |  0.075     |
| Twitter Tweets (Snappy Compressed) | 5    |  0.047     |
| Instagram Photos                   |12319 |  114.57    |
| YouTube Videos                     |50458 |  469.26    |

Reference: <br />
Failure rate is 0.93% as per https://www.backblaze.com/b2/hard-drive-test-data.html<br />
Failures = HD * Failure_Rate<br />
1. 8 * 0.0093 = 0.0744<br />
2. 5 * 0.0093 = 0.0465<br />
3. 12319 * 0.0093 = 114.57<br />
4. 50458 * 0.0093 = 469.26<br /><br />

#### d. Latency

|                           | One Way Latency      |
|---------------------------|---------------------:|
| Los Angeles to Amsterdam  | 140.367 ms           |
| Low Earth Orbit Satellite | 40 ms                |
| Geostationary Satellite   | 240 - 280 ms         |
| Earth to the Moon         | 1300 ms              |
| Earth to Mars             | 3 - 21 minutes       | 

Reference:<br />
1. https://wondernetwork.com/pings<br />
2. https://www.omniaccess.com/leo/#:~:text=The%20GEO%20latency%20is%20of,and%20an%20essential%20part%20if<br />
3. https://www.satsig.net/latency.htm<br />
4 & 5. https://www.spaceacademy.net.au/spacelink/commdly.htm<br /><br />