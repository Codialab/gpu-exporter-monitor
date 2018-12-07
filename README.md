# GPU Monitoring by DCGM
### owner: [nvidia/gpu-monitoring-tools](https://github.com/NVIDIA/gpu-monitoring-tools)
### customed by: [mynameismaxz](https://story.mymacz.com) @ codialabs
#

## Description (คำอธิบาย)
GPU Monitoring by DCGM เป็นส่วนที่ทำหน้าที่ในการดึงค่าสถิติต่างๆ ที่เกี่ยวข้องกับ GPU (สำหรับเครื่องที่ใช้ NVIDIA GPU) โดยจะดึงค่าที่เกี่ยวข้อง เช่น Memory ที่ใช้อยู่, Memory ที่เหลือทั้งหมด, อุณหภูมิของ GPU ฯลฯ ซึ่งอาศัยการทำงานร่วมกันกับ Prometheus

## Requirement
1. [Docker Engine](https://docker.com)
2. [nvidia-docker](https://github.com/NVIDIA/nvidia-docker)
3. [docker-compose](https://docs.docker.com/compose/)
4. NVIDIA GPU Driver (หาวิธีลงเอาเองเด้อ)
5. Port Available (9100/tcp)

## How to use ? (วิธีใช้งาน)
```/bin/sh
$ git clone https://github.com/Codialab/gpu-exporter-monitor
$ cd gpu-exporter-monitor
$ docker-compose up -d
```
จากนั้นตัว Docker จะทำการ Forward Port ที่ 9100 สำหรับดึงข้อมูล ซึ่งตรงนี้ท่านสามารถที่จะใช้ [Prometheus](https://prometheus.io) หรือ [influxdb](https://github.com/influxdata/influxdb) ในการจัดเก็บข้อมูลเพื่อเอาไปแสดงผลหรือวิเคราะห์ต่อได้

> Blog สอนวิธีการทำ Grafana + Prometheus + node_exporter เร็วๆนี้นะครับ ถ้าว่างจะนั่งเขียนให้ :)

## Warning
อย่าลืมลงตาม Requirement ก่อนนะครับ เบื้องต้นเท่าที่ทดสอบ Ubuntu 16.04 LTS, 18.04 LTS ยังไม่พบปัญหาใดๆ

## Contribute
Pull Request มาได้เลยนะครับ หากมีข้อผิดพลาดประการใดขออภัยมา ณ ที่นี้ด้วยครับ