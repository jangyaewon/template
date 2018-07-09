20180709

- 템플릿
- pusher(채팅방, 채팅방에 join) 
- 별점

    #bootstrap 3
    gem 'bootstrap-sass'# 3버전
    #4버전 gem 'bootstrap','~> 4.1.1'
    
    #font-awesome
    gem 'font-awesome-rails'
    
    #gem 'turbolinks', '~> 5'  -> 주석처리
    -----------------------------------------------------------------------
    $ bundle install
    $ rails g controller home index
    ----------------------------------------------------------------------
    #route에서
    root 'home#index'
    
    #assets/javascripts/application.js
    //= require turbolinks  -> 삭제
    //= require_tree .   -> 삭제
    
    //= require bootstrap -> 추가
    ----------------------------------------------------------------------
    #assets/javascripts/application.scsss    
    @import 'bootstrap';
    @import 'font-awesome';
    
    ----------------------------------------------------------------------
     #home.scss에 css이름을 붙여넣는다.   
    
    @import 'font-awesome.min';
    @import 'jquery.tagsinput';
    @import 'owl.carousel';
    @import 'styles';
    @import 'responsive';
    
    # vendor/stylesheets에 위에 쓴 css파일을 집어넣는다.
    
    ----------------------------------------------------------------------
    $ rake assets:precompile
    $ rake assets:clobber  # 위 명령어 지우기
    ----------------------------------------------------------------------
    #config/initilizers/ assets.rb
    Rails.application.config.assets.precompile += %w( home.js 
                                                      home.scss)
    home.coffee를 home.js로 바꾼다.
    ----------------------------------------------------------------------
    $ rake assets:precompile  -> 에러 발생시 이상한 글이 나온다.

        <%= yield %>						-> 해당 위치를 찾아가는
        <%= render 'shared/footer'%>
        </div>
        <%= yield 'javascript_content'%>     -> 블록을 찾아가는


