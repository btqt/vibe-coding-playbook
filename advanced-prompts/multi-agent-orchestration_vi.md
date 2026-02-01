<multi_agent_workflow>
  <agent_1 role="system_architect">
    <responsibility>Thiết kế hệ thống cấp cao và ranh giới component</responsibility>
    <input>Yêu cầu Business và các ràng buộc kỹ thuật</input>
    <output>Kiến trúc hệ thống, các hợp đồng API, sơ đồ luồng dữ liệu</output>
    <specialization>Scalability, performance, kiến trúc security</specialization>
  </agent_1>
  
  <agent_2 role="backend_engineer">
    <responsibility>Thực hiện API và thiết kế lớp dữ liệu</responsibility>
    <input>Thông số kỹ thuật kiến trúc từ agent_1</input>
    <output>Database schemas, các API endpoint, thực hiện business logic</output>
    <specialization>Tối ưu hóa Database, bảo mật API, error handling</specialization>
  </agent_2>
  
  <agent_3 role="frontend_engineer">
    <responsibility>Giao diện người dùng và thiết kế tương tác</responsibility>
    <input>Các hợp đồng API từ agent_2</input>
    <output>React components, quản lý state, các luồng trải nghiệm người dùng</output>
    <specialization>Kiến trúc Component, accessibility, thiết kế responsive</specialization>
  </agent_3>
  
  <coordination_protocol>
    Mỗi agent xác thực đầu ra so với các sản phẩm được giao của agent trước đó trước khi tiếp tục.
    Tất cả các agent phải thống nhất về các giao diện và hợp đồng chung.
    Các quality gate đảm bảo tính nhất quán trên tất cả các lớp thực hiện.
  </coordination_protocol>
</multi_agent_workflow>
