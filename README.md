# reactjs-animation
to animation document or single node using reactjs

How to do:
1, add related react js files
<script src="//fb.me/react-with-addons-0.13.2.js"></script>
<script src="//fb.me/JSXTransformer-0.13.2.js"></script>

and css 
  <style type="text/css">
    body {
      color: #222;
      font-family: "Helvetica Neue", sans-serif;
      font-weight: 200;
      margin: 0 50px;
    }

    .react-draggable, .cursor {
      cursor: move;
    }
    .no-cursor {
      cursor: auto;
    }
    .cursor-y {
      cursor: ns-resize;
    }
    .cursor-x {
      cursor: ew-resize;
    }

    .react-draggable strong {
      background: #ddd;
      border: 1px solid #999;
      border-radius: 3px;
      display: block;
      margin-bottom: 10px;
      padding: 3px 5px;
      text-align: center;
    }
	
	.show {
		display: block;
	}
	.hide {
		display: none;
	}

    .box {
		position:absolute;
      box-sizing: border-box;
      background: #fff;
      border: 1px solid #999;
      border-radius: 3px;
      width: 180px;
      height: 180px;
      margin: 10px;
      padding: 10px;
      float: left;
    }

.example-enter {
  opacity: 0.01;
}

.example-enter.example-enter-active {
  opacity: 1;
  transition: opacity 2000ms ease-in;
}

.example-leave {
  opacity: 1;
}

.example-leave.example-leave-active {
  opacity: 0.01;
transition: opacity 1000ms ease-in;
/*    -webkit-transform: translate3d(100%, 0, 1px);
    transform: translate3d(100%, 0, 0);
    -webkit-transition-duration: .5s;
    transition-duration: .5s;  */
}

  </style>

2, add JSX scripts
//-----------------------------------------------------
  var ReactTransitionGroup = React.addons.CSSTransitionGroup;

var HelloWorld = React.createClass({
  getInitialState: function() {
    return { mounted: false };
  },
  componentDidMount: function() {
    this.setState({ mounted: true });
  },
  render: function() {
    var child = this.state.mounted ? <h1>Hello world</h1> :  null;

    return (
      <ReactTransitionGroup transitionName="example">
        {child}
      </ReactTransitionGroup>
    );
  }
});
var ddd = document.createElement("div");
document.body.appendChild(ddd);
React.render(<HelloWorld />, ddd);

//-----------------------------------------------
That's it. It's super easy.
Do remember that you must set the state mounted to true or false after the node is mounted, otherwise there will be no animation.

Just copy all codes to a seperate HTML file, and run on a webserver.

Enjoy.
