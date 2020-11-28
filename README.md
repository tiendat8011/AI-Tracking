# Bài tập Project 4 AI Ghostbusters
## Đề bài :  http://ai.berkeley.edu/tracking.html

## Điểm autograder
- **Question** q1: 3/3
- **Question** q2: 4/4
- **Question** q3: 3/3
- **Question** q4: 3/3
- **Question** q5: 4/4
- **Question** q6: 4/4
- **Question** q7: 4/4
- **Total**: 15/25

## Question1 
- Với mỗi phần tử p trong self.legalPositions, nếu noisyDistance là none, có nghĩa là pacman đã ăn con ma và vị trí của ma, cập nhật "jail" nơi ma bị ăn, nếu không thì cập nhật belief dựa vào khoảng cách từ ma đến p.

## Question2 
- Với mỗi phần tử p trong self.legalPositions, duyệt mảng lấy phân phối về nơi ma sẽ đến tiếp theo, cập nhật belief.

## Question3 
- Với những action trong legal, lấy vị trí của successor, duyệt những vị trí con ma sống trong livingGhostPositionDistributions, lấy vị trí của con ma có khả năng cao nhất, tính khoảng cách, nếu vị trí đó khác 0, cập nhật giá trị value cho action đó.

## Question4 
- Hàm initializeUniformly(self, gameState): liệt kê các vị trí của con ma có thể có, thiết lập các vị trí cụ thể.
- Hàm getBeliefDistribution(self): lấy beliefDistribution bằng Couter(). Vì các con ma được phân bố chuẩn khắp các ví trí đặt belief bằng 1 có nghĩa là particle có thể ở bất cứ đâu trong grid.
- Hàm observe(self, observation, gameState): Nếu noisyDistance là none, thì cập nhật vị trí particle là vị trí jail của con ma. Nếu không cập nhật belief giống như đã implement trong class exactInference.

## Question5
- Với mỗi i trong range(self.numParticles), lấy tất cả các vị trí của con ma, lấy mẫu vị trí cho 1 số particle.

## Question6
- Hàm initializeParticles(self): liệt kê tất cả những vị trí hợp lệ, tráo ngẫu nhiên.
- Hàm getBeliefDistribution(self): duyệt từng particle trong self.particles, với mỗi giá trị beliefDistribution[particle] cộng thêm 1.0.
- Hàm observeState(self, gameState): Nếu số noisyDistances nhỏ hơn số ma, với mỗi particleIndex trong range(self.numParticles), duyệt từng ghostAgent trong range(self.numGhosts), nếu noisyDistance là none, thì ghost sẽ xuất hiện trong ô tù, nếu không cập nhật lại belief cho mỗi ma. Trong trường hợp tất cả các weight đều bằng 0, lấy mẫu lại từ trước, nếu không lấy mẫu từ các vị trí allPossible. 
## Question7
- Với mỗi i trong range(self.numGhosts), lấy phân bố vị trí cho ma, thêm vào danh sách newParticle mẫu lấy từ phân bố vị trí đó.
